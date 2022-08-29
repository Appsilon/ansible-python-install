# Ansible Python Install

Install Python from source on Ubuntu-based systems (based on RStudio [docs](https://docs.rstudio.com/resources/install-python-source/)).

[![CI](https://github.com/Appsilon/ansible-python-install/workflows/CI/badge.svg)](https://github.com/Appsilon/ansible-python-install/actions/workflows/ci.yml)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-name--of--my--role-blue.svg)](https://galaxy.ansible.com/appsilon/ansible-role-template)

## Requirements

None.

## Role Variables

| Variable        | Required | Default          | Choices                           | Comments                              |
|-----------------|----------|------------------|-----------------------------------|---------------------------------------|
| python_versions | yes      | [3.10.6, 3.9.13] | Array with Python versions >= 3.7 | Version have to be specified as 3.x.y |

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
     - ansible-python-install
```

## License

MIT

## Author Information

[`Appsilon`](https://appsilon.com/)
