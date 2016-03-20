# How-To

```console
# Generate sentry's secret key
docker run --rm sentry generate-secret-key
# Then put it in all variables SENTRY_SECRET_KEY in docker-compose.yml
# Run sentry and friends
docker-compose up -d
# If it is the first run, upgrade the database and create superuser
docker exec -it $(docker ps|grep sentry_1|awk '{print $1}') /docker-entrypoint.sh upgrade
# Access it in browser via http://host:9000
```