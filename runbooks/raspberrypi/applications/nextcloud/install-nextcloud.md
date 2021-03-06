# README #

## Start nextcloud
docker run -d \
    --name cloud \
    -p 8888:80 \
    -v /mnt/raid1/applications/cloud/nextcloud:/var/www/html \
    -v /mnt/raid1/applications/cloud/apps:/var/www/html/custom_apps \
    -v /mnt/raid1/applications/cloud/config:/var/www/html/config \
    -v /mnt/raid1/applications/cloud/data:/var/www/html/data \
    nextcloud:24.0.2

## Upgrade nextcloud

Pull the latest nextcloud version:
`docker pull nextcloud:24.0.2`

Stop the running nextcloud instance:
`docker stop cloud`

Remove the old container:
`docker rm cloud`

Start a new nextcloud instance using the command in the `Start nextcloud` section.

## Monitor upgrade

Check the logs:
`docker logs -f cloud`