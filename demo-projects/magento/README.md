# Magento Docker Test Site Generator
------
**This is NOT meant for production purposes!!**
This should work with all OS as long as you have Docker and Docker Compose installed.  Please report any issues you face and I'll take a look as soon as I can.

-------

### What does it do?
Installs Magento 1.9 (1.9.3.8 to be exact).  Magento 1 reached EOL June 2020 and is no longer being supported by Oracle.

### How do I monitor the app created?
I personally use Docker Desktop but you can use Portainer or any other Docker monitoring tool you want!

### Start Magento 1
Click on the "up" button below to create the app containers.

You then want to run the command below to get the Magento container id to install sample data and start the SSH service
```
docker container ls
```
Find the one that says "alexcheng/magento" and use that for the command below.  This command will install Magento, sample data and an SSH service.
```
docker exec -it <container-id> bash -c "apt-get update; apt-get install dos2unix; dos2unix /usr/local/bin/install-all; /usr/local/bin/install-all; echo -e "root\nroot" | passwd; service ssh restart;"
```

**You will need to run this command each time you start the container to enable ssh**
```
docker exec -it <container-id> service ssh restart
```


### Useful info
**Magento Admin Panel:** 127.0.0.1/admin

**Magento Admin User:** admin

**Magento Admin Pass:** magentorocks1

**SSH Admin User:** root

**SSH Admin Pass:** root