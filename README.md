# wordpress
Create TLS Certificate Manually 
openssl genrsa -out ingress.key
openssl req -new -x509 -key ingress.key -out ingress.crt -days 3650 -subj /CN=wordpress.com
kubectl create secret tls ingress-tls-secret   --cert=ingress.crt --key=ingress.key
