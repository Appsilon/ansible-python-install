# Ansible Python Install

Install Python on Ubuntu and RedHat based systems with Posit's pre-compiled binaries ([docs](https://docs.posit.co/resources/install-python/))

[![CI](https://github.com/Appsilon/ansible-python-install/workflows/CI/badge.svg)](https://github.com/Appsilon/ansible-python-install/actions/workflows/ci.yml)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-appsilon.python_install-blue.svg)](https://galaxy.ansible.com/appsilon/python_install)

## Requirements

None.

## Role Variables

| Variable        | Required | Default          | Choices                           | Comments                              |
|-----------------|----------|------------------|-----------------------------------|---------------------------------------|
| python_versions | yes      | [3.10.6, 3.9.13] | Array with Python versions >= 3.7 | Version have to be specified as 3.x.y |
| python_jupyter_kernel | no      | true | Boolean: true, false | Makes Python available as a Jupyter Kernel |

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  vars:
    python_versions:
      - 3.10.6
      - 3.7.8
  roles:
     - appsilon.python_install
```

## License

MIT

## Author Information

[`Appsilon`](https://appsilon.com/)
