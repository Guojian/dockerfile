
docker build --tag guojian/ubuntu-shadowsocks .

# modify the shadowsocks.json and move to /etc/
docker run --name shadowsocks -p 4433:4433 -v /etc/shadowsocks.json:/etc/shadowsocks.json -d guojian/ubuntu-shadowsocks

#or by default
docker run --name shadowsocks -p 4433:4433 -d guojian/ubuntu-shadowsocks
