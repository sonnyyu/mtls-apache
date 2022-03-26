# Build it:
```bash
git clone https://github.com/sonnyyu/mtls-apache
cd mtls-apache
```
# Use mtls-cert-manage generate server/client/ca certificate 

[https://github.com/sonnyyu/mtls-cert-manage](https://github.com/sonnyyu/mtls-cert-manage)

# Copy Certificate from mtls-cert-manage
```bash
cd ~/mtls-cert-manage/pki
./server.sh
./client.sh
```
# Copy Certificate from mtls-cert-manage
```bash
cd ~/mtls-cert-manage/pki/servercerts 
cp * ~/mtls-apache/certs
cd ~/mtls-cert-manage/pki/clientcerts
cp * ~/mtls-apache/certs
cd ~/mtls-apache/certs
cp 192.168.1.204.crt 192.168.1.204.key ca.crt ~/mtls-apache/httpd/certs
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
cd ~/mtls-apache/certs
curl --cert client1.crt --key client1.key --cacert ca.crt https://192.168.1.204
curl --cert-type P12 --cert client1.p12:p12pass --cacert ca.crt https://192.168.1.204
```
# Install certificate at PC
[Install certificate](https://github.com/sonnyyu/mtls-cert-manage#install-certificate-at-windows)

# Open Browser
```bash
https://192.168.1.204
```
