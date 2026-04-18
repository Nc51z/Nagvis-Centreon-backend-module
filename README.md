# NagVis Centreon Broker Backend

This plugin is a PHP backend class that allows **NagVis** to retrieve monitoring data directly from a **Centreon Broker** database (`centreon_storage`).

## Installation

1. **Upload the file**: Copy `GlobalBackendcentreonbroker.php` to your NagVis installation directory, specifically the classes folder:
   * Example: `/usr/local/nagvis/share/server/core/classes/`

2. **Set Permissions**: Ensure the web server user (e.g., `www-data` or `apache`) has read access to the file.
   ```bash
   chown www-data:www-data GlobalBackendcentreonbroker.php
   chmod 644 GlobalBackendcentreonbroker.php

  Configuration

To enable the backend in NagVis, edit your main configuration file (usually /usr/local/nagvis/etc/nagvis.ini.php) and add the following block:


[backend_centreon]
backendtype="centreonbroker"
dbhost="localhost"
dbport="3306"
dbname="centreon_storage"
dbuser="centreon_user"
dbpass="your_password"
dbinstancename="Central"

Key Parameters:
    dbhost / dbport: The location and port of your MySQL/MariaDB database.

    dbname: The name of the Centreon database (usually centreon_storage).

    dbuser / dbpass: Database credentials with SELECT permissions.

    dbinstancename: The name of your Centreon central poller (matches the name column in the instances table).
