cloudwatch-put
==============

Send some linux metrics to AWS CloudWatch. Based on [aws-mon-linux](https://github.com/moomindani/aws-mon-linux)

Role Variables
--------------

- `cloudwatch_put_user`: User that will run the script (default: 'root')
- `cloudwatch_put_group`: Group that will run the script (default: cloudwatch_put_user)
- `cloudwatch_put_path`: Path to install the script (default: '/opt')
- `cloudwatch_put_set_cron`: Set a cron to send metrics every minute (default: False)
- `cloudwatch_put_aws_bin`: Path to aws bin (default: '/usr/local/bin/aws')
- `cloudwatch_put_opts`: Options passed to script. See script doc for all available options (default: '')
- `cloudwatch_put_access_key`: ACCESS_KEY_ID for aws cli commands (default: '')
- `cloudwatch_put_secret_key`: SECRET_ACCESS_KEY for aws cli commands (default: '')
- `cloudwatch_put_region`: Default AWS region for aws cli commands (default: '')
- `cloudwatch_put_namespace`: Namespace for CloudWatch metric (default: 'Custom-EC2')
- `cloudwatch_put_dimensions`: Dimensions for CloudWatch metric (default: 'InstanceId=${instanceid}')

Dependencies
------------

- dpujadas/ansible-role-awscli

Example Playbook
----------------

    - hosts: servers
      roles:
        - { 
            role: cloudwatch-put,
            cloudwatch_put_set_cron: True,
            cloudwatch_put_opts: '--load-ave1'
        }

License
-------

MIT

[![Build Status](https://travis-ci.org/dpujadas/ansible-role-cloudwatch-put.svg?branch=master)](https://travis-ci.org/dpujadas/ansible-role-cloudwatch-put)
