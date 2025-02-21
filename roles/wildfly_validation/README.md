wildfly validation role
=======================

Role to validate that the app server installed was successful
and the associated systemd service is currently running.

<!--start argument_specs-->
Role Defaults
-------------

| Variable | Description | Default |
|:---------|:------------|:--------|
|`wildfly_user`| posix user account for wildfly | `wildfly` |
|`wildfly_group`| posix group for wildfly | `{{ wildfly_user }}` |
|`wildfly_service_name`| Systemd service name for wildfly | `wildfly` |
|`wildfly_install_workdir`| Wildfly installation directory (where the server files are unzipped) | `/opt/wildfly/` |
|`wildfly_home`| Wildfly installation directory (WILDFLY_HOME) | `{{ wildfly_install_workdir }}wildfly-{{ wildfly_version }}/` |


Role Variables
--------------

* No required variables
<!--end argument_specs-->
