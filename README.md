# OPENHABIAN-STRETCH-2018-FAILED-INITIAL-BOOT-SETUP
OPENHABIAN STRETCH 2018 FAILED INITIAL BOOT SETUP ON RASPBERRY PI 3B+

DEVICE: RPI 3B+

user : openhabian

pass : openhabian

====================================
OPENHABIAN FAILED INITIAL BOOT SETUP
=====================================

[erro no myself failed - resolvido]

sudo rm -rf /opt/openhabian

sudo /boot/./first-boot.sh


[erro java zulu failed - resolvido]

edite o arquivo /opt/openhabian/functions/java-jre.bash
linha 87

sudo nano /opt/openhabian/functions/java-jre.bash

substitua a linha:

cond_redirect wget -nv -O "$jdkTempLocation"/zulu8.tar.gz "$link"

por

cond_redirect wget -nv -O "$jdkTempLocation"/zulu8.tar.gz "https://cdn.azul.com/zulu-embedded/bin/zulu8.40.0.178-ca-jdk1.8.0_222-linux_aarch32hf.tar.gz"

*SALVE E FECHE O ARQUIVO

sudo openhabian-config

	(60) MANUAL/FRESH SETUP
		|-> (62) PACKAGES
		|-> (63) ZULU OPENJDK 32-BITS
		|-> (64) OPENHAB STABLE
		|-> (65) SYSTEM TWEAKS
		|-> (66) SAMBA
		|-> (67) LOG VIEWER
		|-> (68) FIREMOTD
		|-> (69) BASH&VIM SETTINGS

*CONFIRME E CONTINUE CASO SEJA QUESTIONADO.

sudo reboot

sudo mv /boot/first-boot.sh /boot/first-boot.sh.dist

sudo mv /boot/first-boot.log /boot/first-boot.log.dist

sudo openhabian-config

	OPÇÃO (01) UPDATE
	OPÇÃO (02) UPDATE SYSTEM
	OPÇÃO (20) OPTIONAL COMPONENTS
		|-> (21) LOG VIEWER (ELE HABILITA OS LOGS PARA SER VISTO VIA WEB)
	OPÇÃO (20) OPTIONAL COMPONENTS
		|-> (23) MOSQUITTO
			|-> CONTINUE --> <ENTER>
	OPÇÃO (30) SYSTEM SETTINGS
		|-> (32) SET SYSTEM LOCALE
		|-> (33) SET SYSTEM TIMEZONE
		|-> (34) CHANGE PASSWORD
		|-> (36) WIFI SETUP
