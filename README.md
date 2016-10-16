# magerun-setup-example
Just a small module to test how n98-magerun handles errors during setup

# Installation

* Clone the repository ```git clone git@github.com:barbazul/magerun-setup-example.git```
* Change to the directory ```cd magerun-setup-example```
* Install with composer ```php tools/composer.phar install```
* Install Magento in your preferred method (Magento source is at ```htdocs/```)
* Deploy the module ```tools/modman deploy-all```

Now you are ready to trigger the error.

# Triggering the error

Right now Magento should be correctly installed and the SemExpert_FailSetup module should be deployed but not installed

If you run ```php tools/n98-magerun.phar sys:setup:run``` installation will fail because the only installer in the module just throws an exceptin.

Run ```php tools/n98-magerun.phar sys:setup:run || { echo "Exit code was NOT 0" ; exit 1 ; }```

# Expected result

* Standard n98-magerun output for a failed setup (Error message, stack trace and file contents)
* Message "Exit code was NOT 0"
* Exit code 1

# Actual result

* Standard n98-magerun output for a failed setup (Error message, stack trace and file contents)
* No message
* Exit code 0
