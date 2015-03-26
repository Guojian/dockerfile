
docker build --tag guojian/ubuntu-shadowsocks .

docker run --name shadowsocks -p 4433:4433 -d guojian/ubuntu-shadowsocks
