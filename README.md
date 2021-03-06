Role Name
=========

Ansible role for Download a file using sshpass from a sftp server. Please review the tasks/main.yml first.

Requirements
------------

sshpass and sftp are required.

Role Variables
--------------

        defaults/main.yml        
        rutaRemotaSftp: /bksCCD/ADH_4_2_4/PREREQUISITOS/
        rutaLocalDescarga: /tmp

        Vars in Playbook passed from the role definition:
        v_usr: "{{ V_USR }}"
        v_pass: "{{ V_PASS }}"
        v_server: "{{ V_SERVER }}"
        download_this_file: "{{ V_F }}"
        v_remotePath: "{{ rutaRemotaSftp }}"
        v_localPath: "{{ rutaLocalDescarga }}"


Dependencies
------------

no.

Example Playbook
----------------

	--- 
	- name: DOWNLOAD PROCESS
	  hosts: local
	  user: ansible
	  become: true
	  connection: local

        - role: sshpassDownload
          v_usr: "{{ V_USR }}"
          v_pass: "{{ V_PASS }}"
          v_server: "{{ V_SERVER }}"
          download_this_file: "{{ V_F }}"
          v_remotePath: "{{ rutaRemotaSftp }}"
          v_localPath: "{{ rutaLocalDescarga }}"


ansible-playbook --extra-vars '{"V_USR":"myuser", "V_PASS":"mypass", "V_SERVER":"myserver" , "V_F":"myfile"}' --tags "playme" playbook.yml

License
-------

MIT

Author Information
------------------

Miguel Soranno
