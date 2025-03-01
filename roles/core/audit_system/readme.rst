Audit system
------------

Description
^^^^^^^^^^^

This role provides the default auditd configuration which is suitable for RHEL8/CentOS and Ubuntu systems.
Also allows to send the audit logs to the syslog server (cf: https://access.redhat.com/solutions/4986931)
It is as well able to restart auditd service using FQCN module (solve: https://access.redhat.com/solutions/2664811)

Instructions
^^^^^^^^^^^^

Since the auditd manage sensitive data, you need to set the variable audit_system_forward_audit_logs to true to send audit logs to the rsyslog server.

Files:

* /etc/audit/auditd.conf - configuration file for audit daemon
* /etc/audit/audit.rules - audit rules to be loaded at startup
* /etc/audit/plugins.d/syslog.conf - controls the configuration of the syslog plugin

Changelog
^^^^^^^^^
* 1.1.0: Update to pip Ansible. Benoit Leveugle <benoit.leveugle@gmail.com>
* 1.0.2: Configure handler to use FQCN (ansible.builtin.service) module. osmocl <osmocl@osmo.cl>
* 1.0.1: Add Ubuntu 18.04 and 20.04 support. osmocl <osmocl@osmo.cl>
* 1.0.0: Role creation. osmocl <osmocl@osmo.cl>
