### How to configure pyenv and isolate python versions with pyenv.

**pyenv** = is a tool for simple python version management.

1. First we need to install build tools:

```
sudo apt-get install \
    build-essential \
    libsqlite3-dev \
    sqlite3 \
    bzip2 \
    libbz2-dev \
    zlib1g-dev \
    libssl-dev \
    openssl \
    libgdbm-dev \
    libgdbm-compat-dev \
    liblzma-dev \
    libreadline-dev \
    libncursesw5-dev \
    libffi-dev \
    uuid-dev
```

2. Clone `pyenv.git` to `/home/USER/.pyenv`.

```
dev-mentor@devmentor-PC-MK34LEZCBEAD:~$ git clone https://github.com/pyenv/pyenv.git ~/.pyenv
Cloning into '/home/dev-mentor/.pyenv'...
remote: Enumerating objects: 29, done.
remote: Counting objects: 100% (29/29), done.
remote: Compressing objects: 100% (26/26), done.
remote: Total 17440 (delta 10), reused 2 (delta 0), pack-reused 17411
Receiving objects: 100% (17440/17440), 3.40 MiB | 877.00 KiB/s, done.
Resolving deltas: 100% (11857/11857), done.
```

3. Update `~./bashrc` with these environment variables. 

```
dev-mentor@devmentor-PC-MK34LEZCBEAD:~$ echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
dev-mentor@devmentor-PC-MK34LEZCBEAD:~$ echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
dev-mentor@devmentor-PC-MK34LEZCBEAD:~$ echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.bashrc

```
Then reload shell `exec $SHELL`.

4. Create example folder `test`.

```
mkdir test && cd test
```

5. Install python version, e.g `3.7.4`

```
dev-mentor@devmentor-PC-MK34LEZCBEAD:~/Downloads/test$ pyenv install 3.7.4
Downloading Python-3.7.4.tar.xz...
-> https://www.python.org/ftp/python/3.7.4/Python-3.7.4.tar.xz
Installing Python-3.7.4...
Installed Python-3.7.4 to /home/dev-mentor/.pyenv/versions/3.7.4
```

6. Displaying available versions `pyenv versions`

```
dev-mentor@devmentor-PC-MK34LEZCBEAD:~/Downloads/test$ pyenv versions
* system (set by /home/dev-mentor/.pyenv/version)
  3.7.4
```

7. Setting local version `pyenv local 3.7.4` or `pyenv global 3.7.4` as global config.

```
dev-mentor@devmentor-PC-MK34LEZCBEAD:~/Downloads/test$ pyenv versions
  system
* 3.7.4 (set by /home/dev-mentor/Downloads/test/.python-version)
```

8. Check active version.

```
dev-mentor@devmentor-PC-MK34LEZCBEAD:~/Downloads/test$ python --version
Python 3.7.4
```

9. Done.


### Other usefull commands

1. To update pyenv and plugins (including pyenv-update itself), just type pyenv update.

```
pyenv update
```

2. Display available python versions.

```
pyenv install -l
```

3. Deactivate active virtual environment.

```
pyenv deactivate
```

4. Display pyenv commands.

```
pyenv commands
```

### Resources

Pyenv installer : https://github.com/pyenv/pyenv-installer

Alternatives `venv` module : https://docs.python.org/3/library/venv.html

# Next

Basic python3,pip,pipenv,django-admin set-up: https://github.com/boomcamp/setup-pip-pipenv-django-admin-python3
