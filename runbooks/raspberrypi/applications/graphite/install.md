# README #

## Start graphite
docker run -d \
 --name graphite \
 -p 9000:80 \
 -p 2003:2003 \
 -p 8125:8125/udp \
 -v /mnt/raid2/applications/graphite/storage/whisper:/opt/graphite/storage/whisper \
 -v /mnt/raid2/nodes/raspberrypi/configs/graphite/conf:/opt/graphite/conf \
 graphiteapp/graphite-statsd:1.1.10-5


### Mapped Ports
Host	Container	Service
9000	80	nginx
2003	2003	carbon receiver - plaintext
2004	2004	carbon receiver - pickle
2023	2023	carbon aggregator - plaintext
2024	2024	carbon aggregator - pickle
8080	8080	Graphite internal gunicorn port (without Nginx proxying).
8125	8125	statsd
8126	8126	statsd admin
