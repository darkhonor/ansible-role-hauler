# Ansible Role: Hauler

Installs the Rancher Hauler application and (if required) configure the web and
registry server services to run on startup.  Can support an airgap environment.

**THANK YOU** to [Andy Clemenko](https://github.com/clemenko) for the fantastic
[Use Hauler to Air Gap the Rancher Stack](https://github.com/clemenko/rke_airgap_install/tree/main)
project that demonstrated how [Hauler](https://rancherfederal.github.io/hauler-docs/)
can be used in an airgap environment and as a service target on a Linux
system. Please check that projet out!

## Requirements

None

## Role Variables

You can modify any of the following variables as you wish in the role's `defaults/main.yml`:

* `airgap`: Boolean if the target is in an airgap'd environment (Default: `false`)
* `trust_repository_certs`: Boolean if the source repository's certificate is trusted by the target (Default: `true`)

## Dependencies

None

## Example Playbook

Here is an example playbook using this role:

```yaml
- name: Configure workstations
  become: true
  become_method: sudo
  gather_facts: true
  hosts: all
  roles:
    - role: hauler
      airgap: true
      trust_repository_certs: false
```

## License

MIT

## Author Information

Alex Ackerman, GitHub @darkhonor
