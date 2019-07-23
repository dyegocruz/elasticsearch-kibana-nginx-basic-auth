# elasticsearch-kibana-nginx-basic-auth
Docker Compose Elasticsearch, Kibana and Nginx Auth Basic

### 1: Setting Config for Elastic ###

```
echo vm.max_map_count=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
```

### 2: Creating a Nginx password file ###

OBS: Verify that apache2-utils (Debian, Ubuntu) or httpd-tools (RHEL/CentOS/Oracle Linux) is installed.

Create a password file and a first user. Run the htpasswd utility with the -c flag (to create a new file), the file pathname as the first argument, and the username as the second argument:

```
sudo htpasswd -c ./.htpasswd user1
```

Create additional user-password pairs. Omit the -c flag because the file already exists:

```
sudo htpasswd ./.htpasswd user2
```

[More in Nginx](https://docs.nginx.com/nginx/admin-guide/security-controls/configuring-http-basic-authentication/)

### 3: Exec sh to start ###
```
./start.server.sh
```
