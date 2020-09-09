# Set EC2 instance hostname based on tag:Name

Features:

* Use tag:Name to set instance hostname.
* Optional reboot

## Requirements

```bash
pip install ansible boto3 boto
```
## Variables

```yaml
vars:
aws:
  profile: "{{ aws_profile }}"
  region: "{{ aws_region }}"
  tags:
    ansible_managed_hostname: "yes"
reboot: "false"
```

## Example Usage

Add the following to a file like `playbook.yaml`:

```yaml
- hosts: monitoring
  roles:
    - role: "mateothegreat.aws_ec2_hostname"
      vars:
        aws:
          profile: "{{ aws_profile }}"
          region: "{{ aws_region }}"
          tags:
            ansible_managed_hostname: "yes"
        reboot: "false"
```

Run with `ansible-playbook -i <your inventory file> playbook.yaml`.

# Contact

You can reach out to me at https://matthewdavis.io.
