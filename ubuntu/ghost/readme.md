# move production config to /home/ubuntu/ghost/
docker run --name ghost -v /home/ubuntu/ghost:/var/lib/ghost -e NODE_ENV=production -p 80:2368 -d ghost
