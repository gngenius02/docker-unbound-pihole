# docker-unbound-pihole

Usage:
```bash
echo "WEBPASSWORD=CreateAPasswordHere" > .env

cd dockerImage
docker build -t unboundpihole .

cd ..
docker compose up -d
```
