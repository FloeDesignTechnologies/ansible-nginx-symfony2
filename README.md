Role Name
========

Very simple role to configure a symfony2 site with nginx.

Requirements
------------

Have nginx installed beforehand. This role does not install nginx and does not control nginx. This role expects an handler named 'reload nginx' to exists.
This role also expects php-fpm to be installed and expose a unix socket (or an IP:PORT) to connect to.

Role Variables
--------------

    nginx_sf2:
        - name:
          socket:
          root:
          error_log:
          access_log:
          port:
          ssl_key:
          ssl_certificate:


Example Playbook
-------------------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: nginx-symfony2
           nginx_sf2:
            - name: Super cool Sf2 site
              socket: /var/run/php5-fpm.sock
              root: /var/www/

            - name: Super cool SECURE sf2 site
              root: /var/www/
              port: 443
              ssl_key: /etc/nginx/ssl/key.pem
              ssl_certificate: /etc/nginx/ssl/cert.crt
              

License
-------

Apache v2

Author Information
------------------

Pierre Paul Lefebvre - Pheromone - lefebvre@pheromone.ca
