# echo "username    *           password    *" > chap-secrets

mv chap-secrets /etc/

docker run -d --privileged --name pptpd -p 1723:1723 -v /etc/chap-secrets:/etc/ppp/chap-secrets mobtitude/vpn-pptp
