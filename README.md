Vagrant The Hover Labs
----------------------

Vagrant environment for testing The Hover v6.1 easier and better than working with a local
setup.

**Do not use this in production.**

Getting Started
---------------

1. If you haven't got it, install **`Vagrant`**.
2. If you haven't got it or another **`Vagrant-supported`** virtualization package, install **`VirtualBox`** (recommended).
3. Download a box file **`thehoverlabs_v6.1.5.box`** (provided by your instructor).
3. Make a directory to work, example mkdir **`thehover-labs`** and move the box file inside.
4. Setup the vagrant box by typing: ```vagrant box add thehoverlabs thehoverlabs_v6.1.5.box```
5. Copy the **`Vagrantfile`** (provided here) into directory already created before.
6. Start vm: ```vagrant up```
7. Connect to vagrant virtual-machine: ```vagrant ssh```

In order to use this lab the instructor will start your environment for you (Riak, The Hover).

Configuration Notes
------------------

- **`Riak version 2.1`** installed and ready to use for **`The Hover`**.
- **`The Hover 6.1`** installed and ready to use, API listener on localhost:80 and certificates are provided
by your instructor.
