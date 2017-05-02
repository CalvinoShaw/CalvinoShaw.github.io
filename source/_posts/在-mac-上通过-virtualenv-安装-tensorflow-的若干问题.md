---
title: 在 mac 上通过 virtualenv 安装 tensorflow 的若干问题
date: 2017-04-30 23:15:30
tags: tencorflow
---

[I try to install tencorflow via virtualenv in mac, the reference is here:](https://www.tensorflow.org/versions/r0.12/get_started/os_setup.html#virtualenv-installation)

- for I have python already, so I install virtualenv by:
  `sudo pip install --upgrade virtualenv`

- build a new virtualenv environment in `~/development project/tensorflow`, not in `~/`tencorflow as is said in the reference: 

  `virtualenv --system-site-packages ~/development project/tensorflow`

  `cd ~/development project/tensorflow`

- active virtualenv by:
  `source bin/activate  # if use bash,and I choose this line to run`

- when I am in virtualenv and run this: 
  `(tensorflow)$ pip install --upgrade <$url_to_binary.whl>`
  it comes out an error:
  `zsh: parse error near '\n'`

- [then I check here to help solve it](http://stackoverflow.com/questions/33673583/installing-tensorflow-in-a-virtualenv-on-osx)
  it says that `<$url_to_binary.whl>` should be replaced by `https://storage.googleapis.com/tensorflow/mac/tensorflow-0.5.0-py2-none-any.whl`, and I do so. And problem gone.

- but, when I try to test tencorflow by cd some dir in tencorflow like: 
  `(tensorflow)$ cd tensorflow/models/image/mnist`
  the dir is not exist.
  so I guess the url I modified cause it, and I try to reinstall virtualenv and tencorflow, to make my install clean.

- tencorflow is successfully uninstalled, but when I remove virtualenv, it booms:
```
Exception:
Traceback (most recent call last):
  File "/usr/local/lib/python2.7/site-packages/pip/basecommand.py", line 215, in main
    status = self.run(options, args)
  File "/usr/local/lib/python2.7/site-packages/pip/commands/uninstall.py", line 76, in run
    requirement_set.uninstall(auto_confirm=options.yes)
  File "/usr/local/lib/python2.7/site-packages/pip/req/req_set.py", line 346, in uninstall
    req.uninstall(auto_confirm=auto_confirm)
  File "/usr/local/lib/python2.7/site-packages/pip/req/req_install.py", line 754, in uninstall
    paths_to_remove.remove(auto_confirm)
  File "/usr/local/lib/python2.7/site-packages/pip/req/req_uninstall.py", line 115, in remove
    renames(path, new_path)
  File "/usr/local/lib/python2.7/site-packages/pip/utils/__init__.py", line 267, in renames
    shutil.move(old, new)
  File "/usr/local/Cellar/python/2.7.12_2/Frameworks/Python.framework/Versions/2.7/lib/python2.7/shutil.py", line 303, in move
    os.unlink(src)
OSError: [Errno 13] Permission denied: '/usr/local/lib/python2.7/site-packages/virtualenv-15.1.0.dist-info/DESCRIPTION.rst'
```
- I delete dir `tencorflow`
- for now I could not uninstall virtualenv neither install it, but it still exist....that's really wired.

- If I run `sudo pip install --upgrade virtualenv` again, it says:
```
  The directory '/Users/Calvino/Library/Caches/pip/http' or its parent directory is not owned by the current user and the cache has been disabled. Please check the permissions and owner of that directory. If executing pip with sudo, you may want sudo's -H flag.
  The directory '/Users/Calvino/Library/Caches/pip' or its parent directory is not owned by the current user and caching wheels has been disabled. check the permissions and owner of that directory. If executing pip with sudo, you may want sudo's -H flag.
  Requirement already up-to-date: virtualenv in /usr/local/lib/python2.7/site-packages
```

- [参考这里](https://github.com/registerguard/registerguard.github.io/wiki/Install-python,-virtualenv,-virtualenvwrapper-in-a-brew-environment)