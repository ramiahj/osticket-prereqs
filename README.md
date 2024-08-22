<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- SQL

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Enable IIS with CGI
- Install PHP manager for IIS
- Install Rewrite Module
- Install C++ Redistributable
- Install MySQL

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/pLTUaBB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To install osTicket, enable IIS (Internet Information Services) with CGI (Common Gateway Interface). CGI is a standard protocol that allows web servers to interface with executable programs or scripts. osTicket uses PHP (a server-side scripting language) to function, and PHP requires CGI. Therefore, enabling IIS with CGI is crucial for osTicket to run smoothly.
To install the PHP manager, download it from the Microsoft website. Once downloaded, run the installation file and follow the prompts to install it on your machine.
</p>
<br />

<p>
<img src="https://i.imgur.com/6cxuTKm.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, install IIS URL Rewrite Module 2. This module rewrites URLs on the fly, which is important for osTicket's functionality. Clean URLs are human-readable URLs that are easier to remember and share. Download it from the Microsoft website and run the installation file.
</p>
<br />

<p>
<img src="https://i.imgur.com/E56Ye2T.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now install PHP itself. To do this, create a brand new folder on the C Drive named "PHP" then download the latest version of PHP from the official website and extract its contents to the "PHP" folder you just created. This folder will contain all the necessary PHP files needed for osTicket to function correctly.
Next, install C++ Redistributable. To do this, download it from the Microsoft website and run the installation file.
</p>
<br />

<p>
<img src="https://i.imgur.com/EzoDLuh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, install a MySQL server. MySQL is a popular open-source database program used to store and manage data. osTicket requires MySQL to store all the ticket-related information. When installing MySQL, opt for a typical setup, which includes the installation of the server and other necessary components.

After the installation, launch the MySQL Server Configuration Wizard to set up the database server. Choose the "standard configuration" option, which sets up the server for general-purpose use. During the configuration process, take note of the password used to set up the server as you will need that later to configure osTicket. 
*Username = root*
</p>
<br />

<p>
<img src="https://i.imgur.com/iEIoLME.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The next step is to register the PHP version with IIS. To do this, open IIS Manager by searching for it in the Windows search bar and run it as an administrator. Once in the IIS Manager console, navigate to the PHP manager and select "Register new PHP version". Select the "PHP-cgi.exe" file in the PHP folder. 

Once completed, you can finish the registration process by navigating to "osTicket Home" and restarting the server on the right side under "Actions". With PHP now registered with IIS, you can proceed with configuring osTicket to use PHP and MySQL.
</p>
<br />

<p>
<img src="https://i.imgur.com/DCOlrBx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To install osTicket, download the latest version from the official website. Once downloaded, extract the contents and copy the "upload" folder to the "c:\inetpub\wwwroot" directory. You can do this by dragging and dropping the folder to its destination. After copying the "upload" folder, rename it to "osTicket". This is the directory where osTicket will be installed and served from. With osTicket installed, you can now access it from a web browser. 
</p>
<br />

<p>
<img src="https://i.imgur.com/Y4fEPwE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To access osTicket, navigate to the IIS Manager console and select the "Default" site. Under the "Default" site, you should see the "osTicket" folder that was created earlier. Once located, open its settings. On the right-hand side, you should see an option to "Browse *:80", click the link to open osTicket in your web browser.
</p>
<br />

<p>
<img src="https://i.imgur.com/rSP13bt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
When you first open osTicket, you may notice that some extensions aren't enabled. To enable the required extensions, go back to the IIS Manager console and navigate to the "Default" site, then click on the "osTicket" folder. Next, double-click the "PHP Manager" option and select "Enable or disable an extension". Here, enable the following extensions: "php_imap.dll", "php_intl.dll", and "php_opcache.dll". After enabling these extensions, refresh the osTicket site in our web browser to observe the changes.
</p>
<br />

<p>
<img src="https://i.imgur.com/ahmkJOI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Rename the "ost-sampleconfig.php" file to "ost-config.php". To do this, navigate to the "C:\inetpub\wwwroot\osTicket\include" directory and locate the "ost-sampleconfig.php" file. This ensures that osTicket can use the configuration file.
After renaming the file, assign appropriate permissions to it. Do this by disabling inheritance and removing all permissions, then adding new permissions for "Everyone" with "All" permissions. This will ensure that osTicket can access the configuration file and read and write data as needed. You should now be able to continue setting up osTicket in your web browser. Navigate to the osTicket site and click on the "Continue" button.
</p>
<br />

<p>
<img src="https://i.imgur.com/0nptbDq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, enter a name for your helpdesk in the designated field.
Finally, enter a default email address in the appropriate field. This email will be used to receive emails from customers who submit tickets through the osTicket system. It is important to ensure that the email address is correct and actively monitored to ensure timely responses to customer inquiries. Once you've entered the required information, the next step is to set up your database.
</p>
<br />

<p>
<img src="https://i.imgur.com/DkZywB0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and install HeidiSQL, open the application, and create a new session. Do this by clicking on the "New" button in the toolbar and entering the credentials for our MySQL database.
After creating a new session, connect to it. Once connected, create a new database called "osTicket". To do this, right-click on the main window and select "Create new" > "Database" > Enter "osTicket" as the database name and click on the "OK" button to create the new database. With the database created, you can now finish setting up osTicket. Click "Install Now" on the webpage.
</p>
<br />

<p>
<img src="https://i.imgur.com/qOeKllL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
You have now completed the installation of osTicket. Before concluding, there are a few clean-up steps. Firstly, the "setup" folder at C:\inetpub\wwwroot\osTicket\setup, which contains sensitive information, should be deleted to prevent potential security compromises.
Secondly, it is recommended to set the permission of the "ost-config.php" file located at C:\inetpub\wwwroot\osTicket\include\ost-config.php to "Read" only to prevent unauthorized changes. This step is crucial for ensuring the security of your osTicket installation.
  
With these final steps completed, your osTicket is now fully operational and secure.
</p>
<br />
