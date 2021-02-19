Role Name
=========

A brief description of the role goes here.

Requirements
------------

This role is intended to use on a RHEL system that gets SAP software. So your system needs to be installed with at least the RHEL core packages, properly registered and prepared for HANA or Netweaver installation.

It needs access to the software repositories required to install SAP HANA (see also: How to subscribe SAP HANA systems to the Update Services for SAP Solutions)

You can use the redhat_sap.sap_rhsm Galaxy Role to automate this process

To install SAP software on Red Hat Enterprise Linux you need some additional packages which come in a special repository. To get this repository you need to have one of the following products:

* RHEL for SAP Solutions (premium, standard, developer Edition)
* RHEL for Business Partner NFRs
Click here to achieve a personal developer edition of RHEL for SAP Solutions. Please register as a developer and download the developer edition.

* Registration Link : Here you can either register a new personal account or link it to an already existing personal Red Hat Network account.
* Download Link: Here you can download the Installation DVD for RHEL with your previously registered account
NOTE: This is a regular RHEL installation DVD as RHEL for SAP Solutions is no additional product but only a special bundling. The subscription grants you access to the additional packages through our content delivery network(CDN) after installation.

It is also important that your disks are setup according to the SAP storage requirements for SAP HANA. This BLOG is also quite helpful when sizing HANA systems.

Role Variables
--------------

variables
sap_hana_cockpit_sar_local_path
sap_hana_cockpit_sar_file_name
sap_hana_cockpit_clean_tmp_directory
sap_hana_deployment_xs_org_password
sap_hana_cockpit_sapcar_local_path

Dependencies
------------

Before using this role ensure your system has been configured properly to run SAP applications.

You can use the supported role sap-preconfigure comming with RHEL 7 and 8 with RHEL for SAP Solutions Subscription

The upstream version of this role can be found here

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: sap_hana_cockpit }

Example Inventory
----------------

sap_hana_cockpit_sar_local_path: "{{ sap_hana_mediacheck_mountpoint }}"
sap_hana_cockpit_sar_file_name: "SAPHANACOCKPIT00P_12-70002299.SAR"
sap_hana_cockpit_clean_tmp_directory: true
sap_hana_deployment_xs_org_password: "MyPassw0rd!"
sap_hana_cockpit_sapcar_local_path: "/hana/shared/{{sap_hana_ha_pacemaker_hana_sid}}/global/hdb/saphostagent_setup"

License
-------

GPLv3

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
