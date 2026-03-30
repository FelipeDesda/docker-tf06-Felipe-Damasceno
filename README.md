# Saída do Terminal
## docker-compose up -d
### [+] Building 5.8s (9/9) FINISHED
 => [internal] load local bake definitions                                                                         0.0s
 => => reading from stdin 562B                                                                                     0.0s
 => [internal] load build definition from Dockerfile                                                               0.1s
 => => transferring dockerfile: 122B                                                                               0.0s
 => [internal] load metadata for docker.io/library/nginx:alpine                                                    1.7s
 => [auth] library/nginx:pull token for registry-1.docker.io                                                       0.0s
 => [internal] load .dockerignore                                                                                  0.1s
 => => transferring context: 2B                                                                                    0.0s
 => CACHED [1/2] FROM docker.io/library/nginx:alpine@sha256:e7257f1ef28ba17cf7c248cb8ccf6f0c6e0228ab9c315c152f9c2  0.1s
 => => resolve docker.io/library/nginx:alpine@sha256:e7257f1ef28ba17cf7c248cb8ccf6f0c6e0228ab9c315c152f9c203cd34c  0.1s
 => [2/2] RUN apk add --no-cache iputils                                                                           1.8s
 => exporting to image                                                                                             0.9s
 => => exporting layers                                                                                            0.3s
 => => exporting manifest sha256:7baef5ae4259e17fab3190fd527fefed11a3767e82fa2bfebb6a3d60c0b81216                  0.1s
 => => exporting config sha256:b0cba947f66f56732d392fa57ad65dcf8795f6917027ef1ded3e4611404c0f9e                    0.1s
 => => exporting attestation manifest sha256:515ed8d3b255ce4f26cee50bcc45e74ec228bf304ff6aa53145f1bc3edf75c6b      0.1s
 => => exporting manifest list sha256:d653df4b6ebc3f46a9f0ccaf168f33606560f18fa772ebadb311c931862d1e77             0.0s
 => => naming to docker.io/library/lab_compose_tf06-web:latest                                                     0.0s
 => => unpacking to docker.io/library/lab_compose_tf06-web:latest                                                  0.1s
 => resolving provenance for metadata file                                                                         0.0s
[+] up 5/5
 ✔ Image lab_compose_tf06-web         Built                                                                         6.1s
 ✔ Network lab_compose_tf06_default   Created                                                                       0.1s
 ✔ Volume lab_compose_tf06_redis_data Created                                                                       0.1s
 ✔ Container cache_redis              Started                                                                       1.2s
 ✔ Container web_nginx                Started       

 ## docker-compose ps
 ### ll be ignored, please remove it to avoid potential confusion
NAME          IMAGE                  COMMAND                  SERVICE   CREATED              STATUS              PORTS
cache_redis   redis:alpine           "docker-entrypoint.s…"   cache     About a minute ago   Up About a minute   6379/tcp
web_nginx     lab_compose_tf06-web   "/docker-entrypoint.…"   web       About a minute ago   Up About a minute   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp

## docker exec -it web_nginx sh 
## ping cache
### PING cache (172.18.0.2) 56(84) bytes of data.
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=1 ttl=64 time=1.02 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=2 ttl=64 time=0.192 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=3 ttl=64 time=0.160 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=4 ttl=64 time=0.184 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=5 ttl=64 time=0.161 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=6 ttl=64 time=0.116 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=7 ttl=64 time=0.070 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=8 ttl=64 time=0.200 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=9 ttl=64 time=0.057 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=10 ttl=64 time=0.092 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=11 ttl=64 time=0.177 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=12 ttl=64 time=0.166 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=13 ttl=64 time=0.169 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=14 ttl=64 time=0.124 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=15 ttl=64 time=0.321 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=16 ttl=64 time=0.097 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=17 ttl=64 time=0.169 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=18 ttl=64 time=0.099 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=19 ttl=64 time=0.171 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=20 ttl=64 time=0.165 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=21 ttl=64 time=0.334 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=22 ttl=64 time=0.159 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=23 ttl=64 time=0.170 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=24 ttl=64 time=0.164 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=25 ttl=64 time=0.169 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=26 ttl=64 time=0.130 ms
64 bytes from cache_redis.lab_compose_tf06_default (172.18.0.2): icmp_seq=27 ttl=64 time=0.163 ms
^C
--- cache ping statistics ---
27 packets transmitted, 27 received, 0% packet loss, time 26615ms
rtt min/avg/max/mdev = 0.057/0.192/1.019/0.172 ms
