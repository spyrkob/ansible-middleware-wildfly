===========================================
middleware_automation.wildfly Release Notes
===========================================

.. contents:: Topics

This changelog describes changes after version 0.0.7.

v1.4.3
======

Minor Changes
-------------

- Use alternatives instead of rpm to determine java_home `#149 <https://github.com/ansible-middleware/wildfly/pull/149>`_

v1.4.2
======

Minor Changes
-------------

- Remove unrequired vars from playbooks/playbook.yml `#144 <https://github.com/ansible-middleware/wildfly/pull/144>`_

v1.4.0
======

Major Changes
-------------

- wildfly_driver: remove defaults in favor of required parameters `#138 <https://github.com/ansible-middleware/wildfly/pull/138>`_
- wildfly_driver: rename parameters from ``jdbc_*`` to ``wildfly_driver_*`` `#142 <https://github.com/ansible-middleware/wildfly/pull/142>`_

Minor Changes
-------------

- Cleanup and reorganize Prospero playbooks `#136 <https://github.com/ansible-middleware/wildfly/pull/136>`_
- Update to Wildfly 29 `#135 <https://github.com/ansible-middleware/wildfly/pull/135>`_

Bugfixes
--------

- Fix validation role so it can be used with remote nodes. `#131 <https://github.com/ansible-middleware/wildfly/pull/131>`_
- Set ``wildfly_offline_install`` default to False, ``eap_apply_cp`` to True `#133 <https://github.com/ansible-middleware/wildfly/pull/133>`_
- Update references to ``split`` filter `#140 <https://github.com/ansible-middleware/wildfly/pull/140>`_
- Update yaml_configuration syntax (became less permissive) `#130 <https://github.com/ansible-middleware/wildfly/pull/130>`_
- Workaround java-11 bugzilla #2224411 `#127 <https://github.com/ansible-middleware/wildfly/pull/127>`_

v1.3.4
======

Minor Changes
-------------

- wildfly_systemd: detect Java home path on different os_family `#125 <https://github.com/ansible-middleware/wildfly/pull/125>`_

Bugfixes
--------

- Do not re-download elytron adapter if present `#124 <https://github.com/ansible-middleware/wildfly/pull/124>`_

v1.3.3
======

Minor Changes
-------------

- Check that systemd is running and pidfile exists `#117 <https://github.com/ansible-middleware/wildfly/pull/117>`_
- elytron_adapter: skip download if file is already present `#120 <https://github.com/ansible-middleware/wildfly/pull/120>`_
- wildfly_systemd: accept same default vars as wildfly_install `#111 <https://github.com/ansible-middleware/wildfly/pull/111>`_

Bugfixes
--------

- '.Beta' in version: the dot is only optional `#119 <https://github.com/ansible-middleware/wildfly/pull/119>`_
- ISSUE116 - PID File Creation Failure `#118 <https://github.com/ansible-middleware/wildfly/pull/118>`_

v1.3.2
======

Minor Changes
-------------

- Add check for offline installs and allow to specify custom xml config `#108 <https://github.com/ansible-middleware/wildfly/pull/108>`_
- Add support for firewalld `#106 <https://github.com/ansible-middleware/wildfly/pull/106>`_
- Implement JBossNetwork API client for downloading install archives `#107 <https://github.com/ansible-middleware/wildfly/pull/107>`_
- Install: add prospero as alternative install mechanism `#102 <https://github.com/ansible-middleware/wildfly/pull/102>`_
- Update default Wildfly version to 28 `#103 <https://github.com/ansible-middleware/wildfly/pull/103>`_

v1.3.1
======

Minor Changes
-------------

- Remove dependency to community.general (not required) `#100 <https://github.com/ansible-middleware/wildfly/pull/100>`_

v1.3.0
======

Minor Changes
-------------

- Apply cp options `#99 <https://github.com/ansible-middleware/wildfly/pull/99>`_

v1.2.2
======

Major Changes
-------------

- wildfly_install: (eap) apply_cp does not depend on systemd `#90 <https://github.com/ansible-middleware/wildfly/pull/90>`_

Minor Changes
-------------

- Add elytron adapter install (EAP) `#92 <https://github.com/ansible-middleware/wildfly/pull/92>`_
- wildfly-systemd: yaml configuration extension accept templates `#91 <https://github.com/ansible-middleware/wildfly/pull/91>`_

Bugfixes
--------

- Correctly handle server restarts post apply_cp and keycloak_adapter `#94 <https://github.com/ansible-middleware/wildfly/pull/94>`_

v1.2.1
======

Release Summary
---------------

Patch release with internal changes only.


v1.2.0
======

Major Changes
-------------

- Propagate wildfly_install defaults to driver, systemd and utils roles `#80 <https://github.com/ansible-middleware/wildfly/pull/80>`_

Bugfixes
--------

- Become in "Check local download archive path" `#74 <https://github.com/ansible-middleware/wildfly/pull/74>`_
- wildfly_driver: added wildfly_user and wildfly_group to defaults `#77 <https://github.com/ansible-middleware/wildfly/pull/77>`_

v1.1.0
======

Minor Changes
-------------

- Bump version to 1.1.0 to align with downstream (1.1.0 is identical to 1.0.6 upstream) `#67 <https://github.com/ansible-middleware/wildfly/pull/67>`_

v1.0.6
======

v1.0.5
======

Minor Changes
-------------

- Add ``wildfly_java_opts`` to set parameters for wfly JVM `#60 <https://github.com/ansible-middleware/wildfly/pull/60>`_
- Add ``wildfly_statistics_enabled`` var to enable statistics `#58 <https://github.com/ansible-middleware/wildfly/pull/58>`_
- Add variable ``wildfly_bind_addr_private`` to set private iface bind address `#55 <https://github.com/ansible-middleware/wildfly/pull/55>`_
- Add variable ``wildfly_multicast_addr`` to set tcp/udp mcast address `#56 <https://github.com/ansible-middleware/wildfly/pull/56>`_
- Added variable for setting management port bind address `#62 <https://github.com/ansible-middleware/wildfly/pull/62>`_

Bugfixes
--------

- Fix EAP patch apply when yaml configuration is enabled `#59 <https://github.com/ansible-middleware/wildfly/pull/59>`_

v1.0.4
======

Breaking Changes / Porting Guide
--------------------------------

- Rename variable ``instance_id`` to ``wildfly_instance_id`` and update docs `#52 <https://github.com/ansible-middleware/wildfly/pull/52>`_

Bugfixes
--------

- Add become parameter to tasks that require it `#53 <https://github.com/ansible-middleware/wildfly/pull/53>`_

v1.0.3
======

Minor Changes
-------------

- Rename validation role vars to follow proper convention `#48 <https://github.com/ansible-middleware/wildfly/pull/48>`_
- wildfly_driver: make variables as default `#39 <https://github.com/ansible-middleware/wildfly/pull/39>`_

Breaking Changes / Porting Guide
--------------------------------

- Rename jboss_eap role into wildfly_utils to be consistent with role naming convention `#45 <https://github.com/ansible-middleware/wildfly/pull/45>`_

Bugfixes
--------

- JAVA_HOME should be set according to requested JVM package, or overridden via ``wildfly_java_home`` `#46 <https://github.com/ansible-middleware/wildfly/pull/46>`_
- Update included role to new name in rhn installation `#51 <https://github.com/ansible-middleware/wildfly/pull/51>`_

v1.0.2
======

Release Summary
---------------

Minor enhancements, and documentation updates.


v1.0.1
======

Release Summary
---------------

Minor enhancements, and documentation updates.


v1.0.0
======

Release Summary
---------------

This is the first stable release of the ``middleware_automation.wildfly`` collection.

