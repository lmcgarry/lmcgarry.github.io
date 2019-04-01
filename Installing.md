# Installing and configuring an ownCloud Server

## Installing your ownCloud Server from the command line

ownCloud can be installed from the command line as outlined below:

1. Ensure your system meets all the prerequisites. See [System Requirements](https://doc.owncloud.org/server/10.1/admin_manual/installation/manual_installation.html#prerequisites).

2. Download the source files from [here](https://owncloud.org/download/#instructions-server).

3. Unpack the tarball to the required directory.

4. Configure your web server user to be the owner of your unpacked directory as shown in the following example:

`$ sudo chown -R www-data:www-data /var/www/owncloud/`

5. As your [HTTP](https://doc.owncloud.org/server/10.1/admin_manual/installation/manual_installation.html#set-strong-directory-permissions) user, use the `occ` command to perform the installation (example assumes the source was unpacked to `/var/www/owncloud`). 

```
$ cd /var/www/owncloud/
$ sudo -u www-data php occ maintenance:install \
   --database "mysql" --database-name "owncloud" \
   --database-user "root" --database-pass "password" \
   --admin-user "admin" --admin-pass "password"
```

Once the installation is complete, ensure the correct permissions are applied to your ownCloud files and directories. See [Set Strong Directory Permissions](https://doc.owncloud.org/server/10.1/admin_manual/installation/manual_installation.html#set-strong-directory-permissions) for more information.

## Configuring your ownCloud Server

To configure your ownCloud Server, follow these steps:

1. Check the [SELinux configuration](https://doc.owncloud.org/server/10.1/admin_manual/installation/selinux_configuration.html) and modify your SELinux configuration as required.
2. Configure your PHP settings if required. It is recommended to use the default settings. See section on [php.ini](https://doc.owncloud.org/server/10.1/admin_manual/installation/configuration_notes_and_tips.html) for more details.
3. Check your PHP-FPM settings. See section on [PHP-FPM](https://doc.owncloud.org/server/10.1/admin_manual/installation/configuration_notes_and_tips.html) for more details.
4. Ensure you configure your ownClould web server to listen on port 8080.
