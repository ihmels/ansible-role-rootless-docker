Ansible Role: Rootless Docker
=============================

An Ansible Role that installs [Rootless Docker][1] for a user.

Requirements
------------

This role requires that the [prerequisites][2] to run Rootless Docker are fulfilled.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`).

You can control the release channel and the version.

    rootless_docker_channel: 'stable'
    rootless_docker_version: '19.03.12'

If you set the `rootless_docker_channel` variable to _nightly_, `rootless_docker_version` is ignored.

You can also configure in which directory Rootless Docker should be installed.

    rootless_docker_bin_dir: "{{ ansible_env.HOME }}/bin"

Furthermore, you can specify which storage driver should be used.

    rootless_docker_storage_driver: 'vfs'

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: ihmels.rootless_docker }

License
-------

MIT

[1]: https://docs.docker.com/engine/security/rootless/
[2]: https://docs.docker.com/engine/security/rootless/#prerequisites
