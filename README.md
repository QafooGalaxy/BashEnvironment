# BashEnvironment

## Description

Install and configure a proper Bash environment containing proper prompts,
colorschemes, aliases and functions.

## Usage

```yaml
- role: BashEnvironment
  users:
      - { homedir: "/home/jakob", user: "jakob" }
      - { homedir: "/root", user: "root" }
      - { homedir: "/home/benjamin", user: "benjamin", group: "users" }
```

## Configuration

`users`: A list of objects containing definitions for users to be provided with
a proper bash environment. Each object contains the `homedir` and `user` well
as optionally a `group`. If no group is specified it is assumed that `user` and
`group` are the same.

**Example**:
```yaml
users:
    - { homedir: "/home/jakob", user: "jakob", group: "users" }
    - { homedir: "/root", user: "root" }
```

*optional* `bash_prompt_name`: A short banner name displayed *before* every
bash prompt entry. (Default: `VM`).

## Further Remarks

A `.dircolors` theme will be installed to provide proper filetype and directory
coloring for the [Solarized colorscheme](). The colors may look if your
terminal environment is not configured this way.
