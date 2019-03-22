[**HOME**](/index.md)


## Nginx


### /etc/nginx/sites-enabled/default

* You should look at the following URL's in order to grasp a solid understanding
* of Nginx configuration files in order to fully unleash the power of Nginx.
* http://wiki.nginx.org/Pitfalls
* http://wiki.nginx.org/QuickStart
* http://wiki.nginx.org/Configuration


upstream tomcat {
    server 127.0.0.1:8080 fail_timeout=0;
}

server {

	root /var/www/html;

	# Add index.php to the list if you are using PHP
	index index.html index.htm index.nginx-debian.html index.jsp;

	server_name www.bugelhartmann.dk bugelhartmann.dk;

	location / {
		# First attempt to serve request as file, then
		# as directory, then fall back to displaying a 404.
		# try_files $uri $uri/ =404;
		# proxy_pass http://127.0.0.1:8080;
		include proxy_params;
	        proxy_pass http://tomcat/;
	}

	location /nodeapps/ {
		proxy_pass http://127.0.0.1:3000/;
		proxy_http_version 1.1;
		proxy_set_header Upgrade $http_upgrade;
		proxy_set_header Connection 'upgrade';
		proxy_set_header Host $host;
		proxy_cache_bypass $http_upgrade;
	    }

	location /static_content/ {
		root /var/www/html; # now put the static content inside folder: /var/www/html/static_content/
	}


    listen [::]:443 ssl ipv6only=on; # managed by Certbot
    listen 443 ssl; # managed by Certbot
    ssl_certificate /etc/letsencrypt/live/my-domain-here/fullchain.pem; # managed by Certbot
    ssl_certificate_key /etc/letsencrypt/live/my-domain-here/privkey.pem; # managed by Certbot
    include /etc/letsencrypt/options-ssl-nginx.conf; # managed by Certbot
    ssl_dhparam /etc/letsencrypt/ssl-dhparams.pem; # managed by Certbot

}

server {
    if ($host = www.my-domain-here|my-domain-here) {
        return 301 https://$host$request_uri;
    } # managed by Certbot


	listen 80 default_server;
	listen [::]:80 default_server;

	server_name www.my-domain-here my-domain-here;
    return 404; # managed by Certbot


}
