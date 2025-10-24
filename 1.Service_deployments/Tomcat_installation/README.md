# Role: tomcat_install

Installs and configures Apache Tomcat on Ubuntu.

## Variables

- `tomcat_version`: Tomcat version (default: 9.0.73)
- `install_dir`: Installation directory (default: /opt/tomcat)
- `java_package`: Java package to install (default: openjdk-11-jdk)

## Usage

```yaml
- hosts: webservers
  become: yes
  roles:
    - tomcat_install
```
