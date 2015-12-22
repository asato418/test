How to Connect to Services
====================

Add a description such as the following to the hosts file
(`C:\Windows\System32\drivers\etc\hosts` in the case of a Windows machine) of the machine to be
connected to the started CI services (machine that will be a client of the CI services).

Setting example (the acutualIP address must be the IP address of the machine that started the CI services):

```
192.168.1.2 user.pocci.test gitlab.pocci.test jenkins.pocci.test sonar.pocci.test kanban.pocci.test redmine.pocci.test
```


URLs
---

URL                             | Services                                                | Main applications
------------------------------- | ------------------------------------------------------- | ---------------------------------------------
http://gitlab.pocci.test/       | [GitLab](https://gitlab.com/)                           | Code repository management / Ticket (Issue) management
http://jenkins.pocci.test/      | [Jenkins](https://jenkins-ci.org/)                      | CI job management
http://sonar.pocci.test/        | [SonarQube](http://www.sonarqube.org/)                  | Code quality analysis
http://user.pocci.test/         | [phpLDAPadmin](http://phpldapadmin.sourceforge.net/)    | Service user registration
http://kanban.pocci.test/       | [GitLab Kanban Board](http://kanban.leanlabs.io/)       | Kanban board
http://redmine.pocci.test/ (*)  | [Redmine](http://www.redmine.org/)                      | Ticket (Issue) management

(*) If the default configuration is used, access will not be possible because the services will not be started.


Accounts
----------

### Administrators
Service      | User name                  | Password    | Remark
------------ | -------------------------- | ----------- | ------------------
GitLab       | root                       | 5iveL!fe    | From Standard tab
SonarQube    | admin                      | admin       |
Redmine      | admin                      | admin       |
phpLDAPadmin | cn=admin,dc=example,dc=com | admin       |

*   For GitLab, sign in from the **Standard** tab.


### Developers
User name  | Password
---------- | --------
jenkinsci  | password
bouze      | password

*   For GitLab, sign in from the **LDAP** tab.
*   For kanban board, you can click `with http://gitlab.pocci.test/` to log in using the
    OAuth authentication function of GitLab without entering a user name and password.

