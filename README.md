# Your-server-is-running-PHP-version-5.6.3-but-WordPress-5.3.2-requires-at-least-5.6.2.0
Your server is running PHP version 5.6.3 but WordPress 5.3.2 requires at least 5.6.2.0

wp-includes\load.php   
#Your server is running PHP version 5.6.3 but WordPress 5.3.2 requires at least 5.6.2.0

#For this kind of error during installation of WP

Please find the folloring code and update:
1. wp-includes\load.php   
Find: if ( version_compare( $required_php_version, $php_version, '>' ) ) {

Replace with: if ( version_compare( substr($required_php_version, 0,3), substr($php_version,0,3), '>' ) ) {

2. You cannot install because WordPress 5.3.2 requires PHP version 5.6.20 or higher. You are running version 5.6.3.
Learn more about updating PHP.

wp-admin\install.php
Find: $php_compat    = version_compare( $php_version, $required_php_version, '>=' );

Replace with: $php_compat    = version_compare( substr($php_version,0,3), substr($required_php_version,0,3), '>=' );
