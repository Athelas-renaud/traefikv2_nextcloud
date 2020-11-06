# Traefik 2 + Nextcloud with https

Taken from multiple parts of the multiverse, sorry for not crediting...
This have been tested on an AMD X64 Ubuntu (18.04/20.04)

## Requirements

Docker-compose
Modify the passwords, and the domains inside files

## Launch and upgrade
Go into traefik directory:
~~~~
docker-compose pull
docker-compose up -d
~~~~

Repeat into nextcloud directory.

## Ensure PHP.ini configuration:
in your /var/www/html/config/config.php
add the following :

  'trusted_domains' => 
  array (
    0 => 'YOUR_DOMAIN.COM',
  ),
  'overwriteprotocol' => 'https',
  'overwrite.cli.url' => 'https://YOUR_DOMAIN.COM',
  
  
That's it :)
