# Docker installation

A containerised version of the psa_car_controller_fix.
- Docker Hub: https://hub.docker.com/r/raphaelbarreiros/psa_car_controller_fix

### Overview
Once the container is running, the configuration of the psa_car_controller_fix app is near-identical classic Linux/Windows installtion.

### Installation
Create the container, detached, exposing port 5000, and mapping config folder on your host to /config inside the container:

#### With docker-compose
```
docker-compose up -d
```
#### With Docker:
```
docker run -d -ti --name psa_car_controller_fix1 \
  --publish 5000:5000 \
  -v /host_path/config:/config \
  --restart unless-stopped \
  raphaelbarreiros/psa_car_controller_fix
```
Go to http://127.0.0.1:5000 and follow instruction

### Environment variable:
You can modify some parameter with docker environment variable:

|variable         | description                     |
|-----------------|---------------------------------|
|PSACC_CONFIG_DIR | overide configuration directory |
|PSACC_PORT       | change port                     |
|PSACC_OPTIONS    | add cli argurment               |



