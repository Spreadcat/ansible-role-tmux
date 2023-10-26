# spreadcat.tmux

Role that installs and configures tmux locally.

## Requirements

* The role requires `gathered_facts: true` to be set.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
tmux_path_config: "{{ lookup('ansibl.builtin.env', 'HOME') }}/.tmux.conf"
```

Default path to the tmux configuration file. The default is placed in the home directory of the user running the role.

```yaml
tmux_config: []
```

List of lines for the tmux configuration file.

## Other variables

Second class variables, not immediately needed.

```yaml
tmux_pakcages:
 - tmux
```

List of package names that must be present.

```yaml
tmux_owner: "{{ lookup('ansibl.builtin.env', 'USER') }}"
```

Name of the file owner for the tmux configuration.

```yaml
tmux_group: "{{ lookup('ansibl.builtin.env', 'USER') }}"
```

Name of the file group for the tmux configuration.

```yaml
tmux_config_template: tmux.conf.j2
```

Name and path of the template file to use for the configuration file. The template uses the content of the variable `tmux_config`.

## Dependencies

None

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
---
- hosts: all
  vars:
    tmux_config:
      - unbind C-b
      - set -g prefix C-a
  roles:
     - role: spreadcat.tmux
```

## License

BSD

## Author Information

This role is written an maintained by DBV.
