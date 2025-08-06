# Ansible Playbook for ClickHouse and Vector

This playbook installs and configures ClickHouse and Vector on target hosts.

## Requirements

- Ansible 2.9+
- Target hosts with:
  - CentOS/RHEL 7/8
  - Docker (for testing with connection plugin)

## Playbook Structure

- `site.yml` - main playbook
- `prod.yml` - inventory file
- `templates/vector.yml.j2` - Vector configuration template

## Variables

| Variable             | Default                                  | Description             |
|----------------------|------------------------------------------|-------------------------|
| `clickhouse_package` | `clickhouse-common-static-22.3.3.44.rpm` | ClickHouse package name |
| `vector_version`     | `0.22.3`                                 | Vector version          |
| `vector_package`     | `vector-0.22.3-1.x86_64.rpm`             | Vector package name     |

## Tags

- `clickhouse` - tasks related to ClickHouse installation
- `vector` - tasks related to Vector installation

## Usage

1. Edit `prod.yml` with your hosts
2. Run playbook:
   ```bash
   ansible-playbook -i prod.yml site.yml