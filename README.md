# cfn-openvpn-stack
OpenVPN + AWS CloudFormation + Centos7 + Ansible


Ready-to-use OpenVPN server with the option to add and revoke client keys.
Just edit the file `vault_vars/aws`, as example:

    aws:
      aws_access_key: XXXXXXXXXXXXXXXXXXXX
      aws_secret_key: YYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYY
      aws_region_name: eu-west-1
      ec2_key_name: zzzzzzz-zzzzz

And run playbook:

    ansible-playbook install.yml

As result, openvpn keys will be in /tmp/ansible directory:

    $ ls /tmp/ansible/*
    /tmp/ansible/config_client_mynotebook-vpn_eu-west-1_0.tld.ovpn
    /tmp/ansible/config_client_myphone-vpn_eu-west-1_0.tld.ovpn
    /tmp/ansible/config_client_mytv-vpn_eu-west-1_0.tld.ovpn
    /tmp/ansible/config_client_mywork2-vpn_eu-west-1_0.tld.ovpn
