Registering Users
============

When using the incorporated user administration function (user service),
you can register users to the LDAP server as described below.

1.  Access the user service URL (e.g., http://user.pocci.test/) with a browser.
2.  Click **login** on the left side of the screen to display the login screen.

    ![Login Button](images/user-01.png)

3.  Enter the information in **Login DN:** (default: `cn=admin,dc=example,dc=com`) and
    **Password:** (default: `admin`),  and then click the **Authenticate** button
    to log in with administrator permissions.

    ![Login](images/user-02.png)

4.  Click the **+** button on the left of **dc=xxx,dc=xxx*** (`dc=example,dc=com` when default setting)
    on the left side of the screen.

    ![+ Button](images/user-03.png)

5.  Click **Create new entry here**.

    ![Create new entry here](images/user-04.png)

6.  Select `Courier Mail: Account` which is the first template of **Templates:**.

    ![Courier Mail: Account](images/user-05.png)

7.  Enter the user information as shown below and then click **Create Object**.
    *   **Given Name :**    Given name
    *   **Last name :**     Last name
    *   **Common Name :**   User ID
        * This will be entered automatically, but change it to the user ID.
    *   **User ID :**       User ID (Same as for Common Name)
    *   **Email :**         E-mail address
    *   **Password :**      Initial password

8.  The confirmation screen appears. Click **Commit**.
