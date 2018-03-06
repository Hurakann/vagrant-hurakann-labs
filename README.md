Vagrant Hurakann Labs
----------------------

Vagrant environment for testing Hurakann v0.1.1 easier and better than working with a local
setup.

**Do not use this in production.**

Getting Started
---------------

1. If you haven't got it, install **`Vagrant`**.
2. If you haven't got it or another **`Vagrant-supported`** virtualization package, install **`VirtualBox`** (recommended).
3. Download a box file **`hurakannlabs_v0.1.1.box`** (provided by your instructor).
3. Make a directory to work, example mkdir **`hurakann-labs`** and move the box file inside.
4. Setup the vagrant box by typing: ```vagrant box add hurakannlabs hurakannlabs_v6.1.5.box```
5. Copy the **`Vagrantfile`** (provided here) into directory already created before.
6. Start vm: ```vagrant up```
7. Connect to vagrant virtual-machine: ```vagrant ssh```

In order to use this lab the instructor will start your environment for you (Riak, Hurakann).

Configuration Notes
------------------

- **`Riak version 2.1`** installed and ready to use for **`Hurakann`**.
- **`Hurakann 0.1.1`** installed and ready to use, API listener on localhost:80 and certificates are provided
by your instructor.
- **`Certificates`**
    - Account Key: **`jdoe`**
    - Client Key: **`2e4e19bb018f4e7789f34714e5e71fef`**
    - Private Key: **`db25152edde44d4bb371d4db68df186f`**
    - User Id: **`f66cd17945f3442aaea2333a9a259630`**
    - Branch Id: **`f79b81548c4540a1874b2dee2483978f`**

curl Examples
-------------

        curl -i -X POST -H "Ckey: 2e4e19bb018f4e7789f34714e5e71fef" -H "Content-Type: application/json" -d '{"branch_id":"f79b81548c4540a1874b2dee2483978f","coloruser":"black","name":"John","phase":"phase1","user_id":"f66cd17945f3442aaea2333a9a259630","profile_id":"47ce62a69eb843f49e5c5b2d4f012380","lastname":"Doe","_years":30,"_status":"working","_isinhome":false}' "http://localhost/v1/user"

        curl -i -X GET -H "Ckey: 2e4e19bb018f4e7789f34714e5e71fef" "http://localhost/v1/user/search/ql?pagination=15&thql=WHERE%20name:s=John%20INCLUDE%20years,isinhome&branch_id=d3aaaa59a5014db0885a2f5a17964275"

        curl -i -X POST -H "Ckey: 2e4e19bb018f4e7789f34714e5e71fef" -d '{"branch_id":"d3aaaa59a5014db0885a2f5a17964275", "main_user_id":"03f9b81a41b747ae96407a9144ea86a8", "users_id": ["3b1b18b4d33b46b1815296a4f1d9d879"]}' "http://localhost/v1/user/merge"

        curl -i -X GET -H "Ckey: 2e4e19bb018f4e7789f34714e5e71fef" "http://localhost/v1/user/merge?user_id=03f9b81a41b747ae96407a9144ea86a8"
    
