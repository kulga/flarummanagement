## Flarum Management (Basic)

Master Script
https://raw.githubusercontent.com/kulga/flarummanagement/master/flarum_management

In command line instructions. Should be run by **normal** user with *sudo* privileges

```
wget 'https://raw.githubusercontent.com/kulga/flarummanagement/master/flarum_management' -O flarum_management.sh
chmod u+x flarum_management.sh
```



Welcome to my 2nd version of a install script for flarum.
Some features

* Setup of LEMP stack
* Ability to install multiple instances of flarum
  * Supports a ip address or domain names
* Configure flarum with ssl (or not)
  * You may only gain ssl certification with domain names
* Decreased dependance of versions of operating system.
* Ability to remove existing installs and perform cleanup of both ssl and the database
* Ability to reconfigure a existing flarum install with ssl or to remove ssl.

Additionally, the script has been split into functions, making it easier to support alternative distros or software.

Additional notes:

* It uses php7.0

Usage examples:

```
### Invoke help message
./flarum_management
./flarum_management -h
```

```
# Install Flarum site mysite.domain.tld; 
# install myextrasite.domain.tld as well (second command)
./flarum_management -f mysite.domain.tld
./flarum_management -f mysite.domain.tld -f myextrasite.domain.tld
```

```
# Install flarum site with ssl configured. 
# On a existing install, it reconfigures the flarum site with ssl support.

./flarum_management -sf mysite.domain.tld
```

```
# Install LEMP stack; install flarum site with ssl configured as well
./flarum_management -i
./flarum_management -isf mysite.domain.tld
```

```
# Remove flarum site; remove ssl certificate for domain as well
./flarum_management -r mysite.domain.tld
./flarum_management -sr mysite.domain.tld
```

```
# Install LEMP stack, remove flarum site and its domain certificate and install new flarum
# site with ssl configured.
./flarum_management -isr mysite.domain.tld -f myextrasite.domain.tld
```
