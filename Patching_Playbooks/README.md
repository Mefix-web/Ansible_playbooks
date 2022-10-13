Few playbooks that are mainly used to patch servers with dependencies

Playbook called "Playbook_Patching_1_by_1.yml" is a playbook to patch few ubuntu servers with dependencies to check if server comes back to mariadb cluster. If mariadb isn't in sync status then playbooks cancel.

Playbook called "Playbook_Patching"DB&HAProxy_servers.yml" is a playbook to patch few ubuntu servers with dependencies to check if haproxy servers comes back to cluster after reboot. Playbook is checking HAProxy service status and keepalive service status. Additionaly, playbook contains DB servers and is checking if DB servers are coming back to cluster and are synchronized.

Playbook called "Playbook_Patching_servers_with_puppet_dependencies.yml" is a playbook to patch redhat/centos servers that has installed puppet on them. Puppet is monitoring if server A,B,C,D... has file called check.php, if it has then the traffic is moved to those servers. To not have a downtime on application, firstly script stops puppet, switch name of file to other than "check.php", restarts php-fpm service and start patching of the server. During that switch, traffic moves to other server in cluster. Playbook also checks if traffic is switched by looking into access_log and comparing if result is true.

Playbook called "Playbook_Patching_with_solr_service_start.yml" is a playbook to patch redhat/centos servers that has solr service. After patching and rebooting the server, script start solr service and user can verify if service started correctly.