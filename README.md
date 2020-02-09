# Remote Newsletter

Enables  a drupal only site to offer a newsletter subscription to CiviCRM.

### Install `cmr_core`
Remote newsletter uses the CiviCRM rest api and the Drupal module `cmrf_core`, a remote integration toolkit. So this module must installed and configured:

1. Download `cmrf_core` from `https://github.com/CiviMRF/cmrf_core`.
2. Complete the installation with `composer` as described in `https://github.com/CiviMRF/cmrf_core#install`. Composer adds a number of local libraries to the install. So if the hosting provider does not support composer, do the install locally on a development machine and copy the complete module to the server.
3. Enable the drupal module `CMRF Core` core module.

### Configure a Connection Profile

The remote newsletter needs a connection profile of the type `Remote Connection` where the credentials of the rest api are stored.
* Open the configuration screen `<server>admin/config/civimrf/profiles`.
* Add the credentials (for more documentation about this see `https://docs.civicrm.org/dev/en/latest/api/interfaces/#rest-interface`).

### Install  Remote Newsletter

* Install Remote newsletter in the normal Drupal way.
* Open de configuration screen and select the Connection Profile you created in the step before.
* Create a thank you page that the user is forwared to after he subscribed to the newsletter.

Remark the module installs two drupal permissions
* _Administer Remote Newsletter Forms_ : needed for access to the setup screen
* _Access Remote Newsletter Forms_: needed to use the subscription and unsubscription forms. In production these needed to be assigned to a public role.

### Install and enable the `remote_newsletter` CiviCRM extensions.

This extension can be found at [GitHub](`https://github.com/CiviCooP/remote-newsletter`) and installation and configuration instructions can be found in the [README](https://github.com/CiviCooP/remote-newsletter/blob/master/README.md).

### Known issues
At the moment the module only supports two languages for newsletters: Spanish and English. To add more languages the function `_remote_newsletter_languages()` can be extended.
