---
title: License Control Center
source: pdf pp. 100-102, sec 9.2*, 9.2.1
summary: Configuring services after installation (landscape administrator password) and using the License Control Center to find the hardware key, import the license file and review licensed users.
---

# License Control Center

You must configure the services you have installed if they are to operate properly.

> **Note**
>
> The first time you configure any service in the service manager, you must enter the landscape administrator password. This is not for authentication purposes, but to obtain the database password. After entering the landscape administrator password once, you do not have to enter it again when configuring other services.

> **Caution**
>
> If you have installed a firewall on the license server, make sure that the firewall is not blocking the port number you use for the license service; otherwise, the license service and SLD cannot work.
>
> In addition, if you are using port X, make sure that you open both port X and port (X+1) in the firewall. For example, if you are using port `40002`, make sure to also open port `40003`.

The license service is a mandatory service that manages the application license mechanism according to the license key issued by SAP. Web access to the license service enables you to do the following:

- Find and copy the hardware key to run your SAP Business One application and apply for SAP licenses
- Import the license file
- View the basic license information

To use your SAP Business One application according to your contract, you are required to install a license key assigned by SAP.

For new installations, you can use the application for a period of 31 days without a license key. After that period, the SAP Business One application needs a license key to run. We strongly recommend that you request a license key immediately after installing the application.

You also must install a new license key whenever any of the following occurs:

- You have additional users or components.
- The hardware key changes.
- The current license expires.
- You installed a new version of SAP Business One.

To avoid accidentally changing the hardware key, do not perform the following actions on the license server computer:

- Formatting the computer and reinstalling Microsoft Windows.
- Changing the computer name.

The following actions are safe and do not change the hardware key:

- Adding a new user logon.
- Changing the computer date or time.
- Changing the hardware configuration.
- Changing the Windows domain.

**Procedure**

1. In a Web browser, navigate to the following URL: `https://<Server Address>:<Port>/LicenseControlCenter` If you have enabled high availability for the license server, navigate to the following URL: `https://<Virtual IP Address>:<port>/LicenseControlCenter` Alternatively, on the *Services* tab in the System Landscape Directory, you can click the license manager link to access the license control center.

   > **Note**
   >
   > - If you use a proxy for your Internet connection, you must add the full hostname or IP address of any Web server (for example, SLD) to the proxy exception list of your Web browser; in other words, do not use a proxy for these addresses.
   > - The URL of the service is case-sensitive.

2. If you have not logged on to the SLD service, in the logon page, enter the landscape administrator name and password, and then choose *Log In*.

   > **Note**
   >
   > The landscape administrator name is case sensitive.

3. The *General Information* area of the *License Service Information* tab displays the details of the license server. If you have not yet obtained a license key, apply to SAP for a license key using the hardware key. If you are a partner, for more information, see *License Guide for SAP Business One 10.0* on the SAP Help Portal (https://help.sap.com/viewer/p/SAP_BUSINESS_ONE_PRODUCT_LINE).
4. To install the license key, on the *License Service Information* tab, choose *Browse*, select the TXT file you received from SAP, and then choose *Import License File*.

   > **Note**
   >
   > CORBA license server now is only the proxy of HTTPS license server for compatibility purposes and may be removed in future patches. We do not recommend you use SAP Business One Service Manager to configure the license service.

5. To view the licensed users or identify inconsistent license allocations, go to the *Licensed Users* tab. The application highlights inconsistent license allocations. Select the relevant rows and choose *Remove Inconsistent License Allocations*. You can clear these inconsistent allocations to free up license space and remove inactive or non-existent users.

   > **Note**
   >
   > A visual indicator appears on the *Licensed Users* tab when one or more inconsistent license allocations are detected. This provides a call for action to administrators to review and resolve license allocation issues.
