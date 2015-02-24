#!/bin/bash

mkdir -p ~/BonjourMadame/

if [[ "$(ping -c 1 8.8.8.8 | grep "100% packet loss" )" != "" ]]; then
	echo "Erreur : vous n'êtes pas connecté à internet"
	exit 1
else
	echo "Récupération de l'image du jour..."
	jour=$(date +%d-%m-%Y)
	wget -q http://bonjourmadame.fr -O - | grep ".media.tumblr.com/" | grep "img" | grep http | cut -d\" -f2 | wget -q -i - -O ~/BonjourMadame/Bonjour_Madame_$jour.jpg
	echo "L'image du jour a été enregistrée dans ~/BonjourMadame/"
fi
