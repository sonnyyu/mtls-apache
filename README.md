# Build it:
```bash
git clone https://github.com/sonnyyu/mtls-apache
cd mtls-apache
```
# Use mtls-cert-manage generate certificate 

[https://github.com/sonnyyu/mtls-cert-manage](https://github.com/sonnyyu/mtls-cert-manage)

# Copy all the certificate 
```bash
cd ~/mtls-cert-manage/cert
cp *   ~/mtls-apache/cert
cp ca.crt localhost.crt localhost.key   ~/mtls-apache/httpd/cert/
```
# Getting started nginx with certificate
```bash
cd ~/mtls-apache
docker-compose up -d 
```
# Quit 
```bash
cd ~/mtls-apache
docker-compose down 
```
# Quit and remove Volume
```bash
cd ~/mtls-apache
docker-compose down -v
```
# Test mTlS
```bash
cd ~/mtls-apache/cert
curl --cert client1.crt --key client1.key --cacert ca.crt https://192.168.1.204
curl --cert client1.crt:password1 --key client1.key --cacert ca.crt https://192.168.1.204
curl --cert-type P12 --cert client1.p12 --cacert ca.crt https://192.168.1.204
```
# Install certificate at PC
[Install certificate](https://github.com/sonnyyu/mtls-cert-manage#install-certificate-at-windows)

# Open Browser
```bash
https://192.168.1.204
```
