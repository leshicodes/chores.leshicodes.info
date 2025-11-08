https://docs.planka.cloud/docs/installation/docker/production-version/

`cp .env.secrets.example .env.secrets`
`openssl rand -hex 64`
copy key into `.env.secrets` under `SECRET_KEY` value
change the `BASE_URL`

`docker compose run --rm planka npm run db:create-admin-user`
sample output: 
```
Email: YOUR_ADMIN_EMAIL
Password: YOUR_ADMIN_PASSWORD
Name: ...
Username (optional): ...
```
Start Services again
```
docker compose up -d
```

Once the services are running, browse to `BASE_URL` and log in as `YOUR_ADMIN_EMAIL` with the password `YOUR_ADMIN_PASSWORD`.

If you're not using Docker volumes and prefer to directly link folders (bind mounts), you'll need to adjust the permissions of those folders. This ensures that the default user running the Node.js application (usually called "node" with a user ID of 1000) can make changes to the files and folders inside. Run the following command to adjust the permissions:
`chown -R 1000:1000 /mnt/path`