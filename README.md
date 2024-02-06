# Ansible Python Install

Install Python (with Jupyter) on Ubuntu and RedHat based systems with Posit's pre-compiled binaries ([docs](https://docs.posit.co/resources/install-python/))

[![CI](https://github.com/Appsilon/ansible-python-install/workflows/CI/badge.svg)](https://github.com/Appsilon/ansible-python-install/actions/workflows/ci.yml)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-appsilon.python_install-blue.svg)](https://galaxy.ansible.com/appsilon/python_install)

## Requirements

If you want to install Workbench's plugins, then the Python used for Jupyter installation needs to be >= 3.7

## Role Variables

| Variable        | Default          | Choices                           | Comments                              |
|-----------------|------------------|-----------------------------------|---------------------------------------|
| python_versions | [3.10.6, 3.9.13] | Array with Python versions >= 3.7 | Version have to be specified as 3.x.y |
| python_jupyter_kernel | true | Boolean: true, false | Makes Python available as a Jupyter Kernel |
| python_jupyter_install | true | Boolean: true, false | Whether to install Jupyter |
| python_jupyter_install_method | virtualenv | String: virtualenv, system | Method of Jupyter installation |
| python_jupyter_python_version | `"{{ python_versions[0] }}"` | One of the versions passed in python_versions  | Used only for virtualenv method |
| python_jupyter_workbench | true | Boolean: true, false | Whether to install Workbench's plugins for Jupyter |

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
