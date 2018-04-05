# phpipam-vagrant
A vagrant environment for phpipam

## To Use

Make sure Vagrant and Virtualbox are installed then simply run `vagrant up`

On first boot the system will clone the repo https://github.com/phpipam/phpipam at the master branch.

`vagrant provision` will cleanup the repo and re-clone but it will not remove the databse.

To remove the database first login to mysql

`mysql -u root -p` : password is `root`

and run `drop DATABASE phipam`

Then run `vagrant provision` and a new database will be created.