---
title: Pictures Folder
source: pdf pp. 116-117, sec 9.2.4
summary: Additional configuration needed to display pictures such as company logos from the pictures folder in the SAP Business One client, including mounting the shared folder on the SBO Mailer Linux server.
---

# Pictures Folder

To display pictures which are stored in the pictures folder in the SAP Business One client, such as company logos, you must perform some additional configurations.

**Procedure**

1. Create a folder on a Windows machine and grant full permission to the folder, for example: `\\server\folder\shared_folder`.
2. Log in to the SAP Business One client. On the *Path* tab of the *General Settings* window (*Main Menu* > *Administration* > *System Initialization* > *General Settings*), specify `\\server>\folder\shared_folder` as the picture folder.
3. In the SQL Server Management Studio, execute the following query against the company database in question: `select "BitmapPath" from OADP` The result looks like the following: "`\\server\folder\shared_folder`".
4. Copy the query result to a text editor, remove the file name, and replace the backslash (\) with the forward slash (/). The result is the shared folder path saved in the database, for example: `//server/folder/shared_folder`.
5. Log in to the Linux server where SBO mailer is deployed as `root` and do the following:
   1. Create an empty folder, for example: `/mnt/sharedpicture`.

      > **Caution**
      >
      > The name of the mount point must not contain underscores (_).
      >
      > - Correct example: `/mnt/sharedpicture`
      > - Incorrect example: `/mnt/shared_picture`

   2. Mount the folder in step 4 to the empty folder, using the following command:

      ```bash
      mount -t cifs -o user=b1service0,pass=b1service0 '//server/folder/
      shared_folder' /mnt/sharedpicture
      ```

      > **Note**
      >
      > The user (`b1service0`) and the relevant password in the command are for a Windows machine user in step 1.
