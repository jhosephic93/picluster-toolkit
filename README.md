# Raspberry PI4
### Instalacion y configuracion de Raspberry PI4
Link -> https://ubuntu.com/tutorials/how-to-install-ubuntu-on-your-raspberry-pi#4-boot-ubuntu-server

### Mapear IP de Raspberry PI4
```console
$ sudo nmap -sn 192.168.1.*
```

### Configuracion de red.

```console
$ sudo nano /etc/netplan/50-cloud-init.yaml
```
##### Forma/Version nueva y/o actualizada.
```yaml
network:
    version: 2
    ethernets:
        eth0:
            optional: true
            dhcp4: false
            addresses:
            - 192.168.1.20/24
            routes:
             - to: default
               via: 192.168.1.1
            nameservers:
                addresses:
                - 8.8.8.8
```
##### Forma deprecated/obsoleta.
```yaml
network:
    version: 2
    ethernets:
        eth0:
            optional: true
            dhcp4: false
            addresses: [192.168.1.2/24]
            gateway4: 192.168.1.1
            nameservers:
                addresses: [8.8.8.8,8.8.4.4]
```

### Run

```console
$ sudo netplan apply
$ sudo reboot
```

## Install Desktop on Ubuntu 22.04

```console
$ sudo apt install xubuntu-desktop
###En caso de error volver a correr el mismo script
###Select gddm3
```
