# Ansible Playbook for Debian stretch

## test with self-signed certificate

### generate

- `sudo mkdir -p /var/lib/dehydrated/certs/localhost`
- `sudo openssl genrsa -out /var/lib/dehydrated/certs/localhost/privkey.pem 4096`
- `sudo openssl req -x509 -subj /CN=localhost -key /var/lib/dehydrated/certs/localhost/privkey.pem -out /var/lib/dehydrated/certs/localhost/fullchain.pem`

### access

- `curl --cacert /var/lib/dehydrated/certs/localhost/fullchain.pem --head https://localhost/`
