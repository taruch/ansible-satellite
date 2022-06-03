# ansible-satellite
These example playbooks are intended to be run in order from a working
RHEL 7.9 system.  The playbooks utilize the redhat.satellite_operations and
redhat.satellite collections to inialize a working Satellite 6.9 server with
content on the system.

It requires access to the internet or another Satellite system for packages
as-is, but if you want to take care of package content on your own, you should
be able to run the remaining playbooks.

--- 1_satellite_pre_install.yml

This playbook sets up the host with the required repositories, installs
the satellite packages, and opens required firewall ports

--- 2_satellite_install.yml

This playbook installs Satellite on the host, and uploads the manifest.  This
requires you to have placed a manifest file in /tmp (/tmp/manifest.zip).  It will
finally refresh the repos after the manifest is uploaded so you are able to find
content in playbook 3.

--- 3_create_content.yml

This playbook will enable repos, and sync the content.

--- 4_configure_lifecycle_env.yml
