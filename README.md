# Your-server-is-running-PHP-version-5.6.3-but-WordPress-5.3.2-requires-at-least-5.6.2.0
Your server is running PHP version 5.6.3 but WordPress 5.3.2 requires at least 5.6.2.0

wp-includes\load.php   
#Your server is running PHP version 5.6.3 but WordPress 5.3.2 requires at least 5.6.2.0

#For this kind of error during installation of WP

/*Please find the folloring code and update:
1. wp-includes\load.php   
Find: if ( version_compare( $required_php_version, $php_version, '>' ) ) {

Replace with: if ( version_compare( substr($required_php_version, 0,3), substr($php_version,0,3), '>' ) ) {
