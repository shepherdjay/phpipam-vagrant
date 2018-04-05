# phpipam-vagrant
A vagrant environment for phpipam

## To Use

#### Quick-Start Latest Version
Make sure Vagrant and Virtualbox are installed then simply run `vagrant up` and wait. Due to the vagrant box I'm
using which I know is friendly to corporate proxies the first time boot takes sometime.

On first boot the system will clone the repo https://github.com/phpipam/phpipam at the master branch and setup
the database. To access the system navigate to http://127.0.0.1:8080

username:password is `admin:admin12345`

#### Stable Version

The vagrant definition also includes configuration for cloning 1.3.1 which is the current latest stable release. To bring
up a box with this version type `vagrant up stable`

#### Reset Environment

`vagrant provision` will cleanup the repo and re-clone but it will not remove the database.

To remove the database first login to mysql

`mysql -u root -p` : password is `root`

and run `drop DATABASE phipam`

Then run `vagrant provision` and a new database will be created.

#### Contributing

If you would like to contribute, especially if you know of how to speed up the initial up proccess, please feel free
to file an issue to discuss the contribution.