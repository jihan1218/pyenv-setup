# pyenv-setup
This is a guidline for `pyenv` in ubuntu environment.

## Install and update dependencies
```console
root@ubuntu:~$ sudo apt update -y
root@ubuntu:~$ sudo apt install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python3-openssl git
root@ubuntu:~$ sudo apt install curl
```

## Install pyenv and setup
```console
root@ubuntu:~$ curl https://pyenv.run | bash
```

If you use bash use `~/.bashrc` instead of `~/.zshrc`.
```console
root@ubuntu:~$ echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
root@ubuntu:~$ echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
root@ubuntu:~$ echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n eval "$(pyenv init -)"\nfi' >> ~/.zshrc
```

Restart the shell
```console
root@ubuntu:~$ exec "$SHELL"
```

## Install python and switch between versions
Check all lists of python versions.
```console
root@ubuntu:~$ pyenv install --list
```

Now, you can install your desired versions. Here I used `3.7.13`.
```console
root@ubuntu:~$ pyenv install 3.7.13
```

You can check all of your installed python versions.
```console
root@ubuntu:~$ pyenv versions
  system
* 3.7.13 (set by /home/root/.pyenv/version)
  3.10.12
```

To change python version to `3.10.12`.
```console
root@ubuntu:~$ pyenv global 3.10.12
root@ubuntu:~$ pyenv init
root@ubuntu:~$ exec "$SHELL"
```

Check your python version.
```console
root@ubuntu:~$ python --version
Python 3.10.12
```

Now you are good to go!!
