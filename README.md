<<<<<<< HEAD
Prezto — Instantly Awesome Zsh
==============================

Prezto is the configuration framework for [Zsh][1]; it enriches the command line
interface environment with sane defaults, aliases, functions, auto completion,
and prompt themes.

Installation
------------

Prezto will work with any recent release of Zsh, but the minimum required
version is 4.3.17.

  1. Launch Zsh:

        zsh

  2. Clone the repository:

  ```
        git clone --recursive https://github.com/deny4ll/prezto.git "${ZDOTDIR:-$HOME}/.zprezto"
  ```
  3. Create a new Zsh configuration by copying the Zsh configuration files
     provided:

     ```
         sh setopt EXTENDED_GLOB
     for rcfile in "${ZDOTDIR:-$HOME}"/.zprezto/runcoms/^README.md(.N); do
       ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"
     done
     ```

  4. Set Zsh as your default shell:

        chsh -s /bin/zsh

  5. Open a new Zsh terminal window or tab.

### Troubleshooting

If you are not able to find certain commands after switching to *Prezto*,
modify the `PATH` variable in *~/.zprofile* then open a new Zsh terminal
window or tab.

Updating
--------

Pull the latest changes and update submodules.

    git pull && git submodule update --init --recursive

Usage
-----

Prezto has many features disabled by default. Read the source code and
accompanying README files to learn of what is available.

### Modules

  1. Browse */modules* to see what is available.
  2. Load the modules you need in *~/.zpreztorc* then open a new Zsh terminal
     window or tab.

### Themes

  1. For a list of themes, type `prompt -l`.
  2. To preview a theme, type `prompt -p name`.
  3. Load the theme you like in *~/.zpreztorc* then open a new Zsh terminal
     window or tab.

     ![sorin theme][2]

Customization
-------------

The project is managed via [Git][3]. It is highly recommended that you fork this
project; so, that you can commit your changes and push them to [GitHub][4] to
not lose them. If you do not know how to use Git, follow this [tutorial][5] and
bookmark this [reference][6].

Resources
---------

The [Zsh Reference Card][7] and the [zsh-lovers][8] man page are indispensable.

License
-------

(The MIT License)

Copyright (c) 2009-2011 Robby Russell and contributors.

Copyright (c) 2011-2015 Sorin Ionescu and contributors.

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

[1]: http://www.zsh.org
[2]: http://i.imgur.com/nrGV6pg.png "sorin theme"
[3]: http://git-scm.com
[4]: https://github.com
[5]: http://gitimmersion.com
[6]: http://gitref.org
[7]: http://www.bash2zsh.com/zsh_refcard/refcard.pdf
[8]: http://grml.org/zsh/zsh-lovers.html
=======
# Ansible Role: Prezto

[![Build Status](https://travis-ci.org/loliee/ansible-prezto.svg?branch=master)](https://travis-ci.org/loliee/ansible-prezto)

Setup prezto zsh framework.

- [zsh documentation](http://www.zsh.org/)
- [prezto](https://github.com/sorin-ionescu/prezto>) [Screenshots](http://mikebuss.com/2014/04/07/customizing-prezto/)

## Requirements

Requires git 2.0.0+ and ZSH 5.0.0+.

- RedHat family
- Debian family
- Darwin (OSX).

## Dependencies

- Role [ansible-git](https://github.com/loliee/ansible-git)
- Role [ansible-zsh](https://github.com/loliee/ansible-zsh)

To install:

add in your `requirements.yml`

```yaml
- src: loliee.zsh
  name: ansible-zsh
  path: ../

- src: loliee.git
  name: ansible-git
  path: ../
```

Run following command to install packages in `roles/` directory.

```bash
ansible-galaxy install -r requirements.yml -p roles --force
```

## Role Variables

### `__users__`

Unset by default, dictionary should defined like this:

```yaml

__users__:
  [username]:
    [option]: [value]
```

**Options**

| Option                   | Type     | Comments                                                    |
|--------------------------|----------|-------------------------------------------------------------|
| prezto_editor            | string   | `vi` or `emacs`. default value is `vi`.                     |
| prezto_install           | boolean  | `Yes` or `No`, default value is `No`.                       |
| prezto_zpreztorc_content | text     | Lines to append to `~/.zpreztorc opts`, modules...          |

### Defaults

Check [defaults/main.yml](defaults/main.yml) for default values.

| Variable                         | Type     | Comments                                            |
|----------------------------------|----------|-----------------------------------------------------|
| prezto_repo_url                  | string   | Prezto git repository url.                          |
| prezto_source                    | string   | How to source prezto in `.zshrc`.                   |
| prezto_zpreztorc_default_content | text     | Default lines to append to `~/.zpreztorc opts`, modules..., if `prezto_zpreztorc_content` no set. |

## Example Playbook

The following playbook will install prezto for root user.

``` yaml
# ./tests/playbooks/main.yml

- hosts: localhost
  remote_user: root
  vars:
    __users__:
      root:
        prezto_install: Yes
```

Run test, make sure ansible-zsh and ansible-prezto are in your role path.

## Run Tests

Require [serverspec](http://serverspec.org/), check [.travis.yml](.travis.yml) for details.

## Licence

MIT © [Maxime Loliée](https://github.com/loliee/)
>>>>>>> f1de2bc65b4b7ec92658af8a2db0b80aa7272bed
