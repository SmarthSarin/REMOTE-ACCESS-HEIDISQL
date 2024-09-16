# REMOTE-ACCESS-HEIDISQL
<BR> Allow remote access over static IP , Database , SQL , Apache 

<BR> To create a user with a username and password for remote access in 
<BR> MySQL or MariaDB using HeidiSQL, follow these steps:

<BR> Open HeidiSQL and Connect to Your Database

<BR>Launch HeidiSQL and connect to your database server as the root user (or any user with administrative privileges).

<BR> Create a New User with Remote Access

<BR> Once connected, in the left-hand panel, locate and right-click on the User Manager option (it's under the "Tools" menu or right-click on the database connection in the panel).

<BR> In the User Manager window:

<BR> Click on the Add button to create a new user.

<BR> Set Up Username, Host, and Password

<BR> User Name: Enter the username for the new user (e.g., newuser).

<BR> Host: Set the host. If you want to allow access from any remote host, enter % as the host. If you want to allow access from a specific IP address or hostname, enter that instead.

<BR> Password: Enter and confirm the password for the user.

<BR> Assign Privileges to the User

<BR>In the Global Privileges tab:

<BR> Select the privileges you want to grant this user. If you want to give the user full access to the database, select "ALL PRIVILEGES."

<BR>In the Database-specific Privileges tab (optional):

<BR> If you only want the user to have access to a specific database, select that database and assign the necessary permissions.

<BR> Save the User

<BR> Once everything is set up, click Save or Apply to create the user.
Grant Remote Access (via SQL) (Optional)

<BR> If you want to do this manually using SQL (or if HeidiSQL lacks certain options):

<BR> Open a query tab in HeidiSQL.

<BR> Run this command to create the user:

<BR> sql
<BR> Copy code
<BR> CREATE USER 'newuser'@'%' IDENTIFIED BY 'password';
<BR> GRANT ALL PRIVILEGES ON . TO 'newuser'@'%' WITH GRANT OPTION;
<BR> FLUSH PRIVILEGES;
<BR> Replace 'newuser' with the desired username and 'password' with the desired password.
<BR> % allows access from any remote IP. You can restrict it by replacing % with a specific IP address.
<BR> Test Remote Connection
<BR> Once the user is created, you can test the remote connection by using HeidiSQL or any other MySQL client.
