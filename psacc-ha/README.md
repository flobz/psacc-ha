# PSA Car Controller

[![Publish Docker image](https://github.com/flobz/psa_car_controller/actions/workflows/Docker_build.yml/badge.svg?branch=master)](https://hub.docker.com/repository/docker/flobz/psa_car_controller)
[![Donate](https://img.shields.io/badge/Donate-PayPal-blue.svg)](https://www.paypal.com/donate?hosted_button_id=SM652WPXFNCXS)

### This is a python program to control a PSA car with connected_car v4 api.
## Install psa_car_controller in Home Assistant

1. In homeassistant go to supervisor panel
2. Then go to "ADD-ON store"
3. On the top right click on the three dot ,then repository
4. Past the following url https://github.com/flobz/psacc-ha 
5. Click on add
6. At the bottom of the page you should see PSA Car Controller
7. Click on it  and install
8. Configure the addon : ![image](https://user-images.githubusercontent.com/48728684/150692985-23da4fbe-cc40-4460-8003-1636b8211f60.png)


You can find more details here : https://www.home-assistant.io/common-tasks/os#installing-third-party-add-ons

## Modify config file
1. [SSH to your raspberry or virtual machine](https://developers.home-assistant.io/docs/operating-system/debugging/#ssh-access-to-the-host)
2. Run the following command 

```shell
docker inspect -f '{{ .Mounts }}' $(docker ps -aqf "name=acc") | grep -o '/mnt/data[^ ]*psacc' 
```
It should return PSACC config path.

4. cd `<path returned by last command>`
5. You can now edit any config file 
```shell
nano charge_config.json                        
nano config.ini                                
nano config.json
```
6. You can also backup the database that contains all trips and charge:
```
cp info.db /root/psacc_db_backup.db
```
## Configure HA Panel
[Look here](https://github.com/Flodu31/HomeAssistant-PeugeotIntegration)

You can find other config example [here](https://community.home-assistant.io/t/peugeot-citroen-ds-cars-connected-car/202949/34)

## Information on the app
Go here : https://github.com/flobz/psa_car_controller
