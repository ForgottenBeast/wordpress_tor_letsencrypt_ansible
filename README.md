# Explanation

This role is used to deploy a docker based wordpress website with a tor hidden
service as well as it's clear web front

# Variables
TOR_HH: True if you want a tor hidden service to be set up too
CLOUDFLARE: True if you only want to accept connections from cloudflare machines

#Tags
* *firewall* configure firewall using iptables_rules and ipsetconf files if
  you want to use cloudflare to prevent direct IP based access
* *wp_setup* Create the initial wordpress docker volumes from clean images
* *wp_volumes_setup*: *ONLY* sets up docker volumes without initializing them
* *wp_all_backup* Create backup files for both site and db
* *wp_backup* Create backup file for wordpress
* *wp_db_backup* Create backup file for db
* *wp_all_restore* restore data from backups for wordpress and db
* *wp_restore* restore data from backups only for wp
* *wp_db_restore* restore data from backups only for db
* *wp_deploy* deploy wordpress container with db
* *show_onion* display onion url when tor_hh is enabled
* *wp_renew* Use when it's time to renew your certificate while using cloudflare
  firewall rules. Pause your site on cloudflare first then run those tasks.

---
# DANGEROUS TAGS
* *wp_destroy*: completely wipes the wordpress installation. Stops the
service, remove the containers and the volumes as well. There will be nothing
left, not even a smoking pair of shoes. *YOU HAVE BEEN WARNED!*
