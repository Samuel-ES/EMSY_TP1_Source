# TP1 - Installation Linux sur une VM - V0.1

## Groupe 

- SVD NTN

## But 

Cette manipulation a pour but d'installer une distribution linux [Sparky Linux](https://sparkylinux.org/) dans une machine virtuelle VMware Workstation Player, à l’aide d’une image disque (ISO).

## Materiels à disposition 

- VMware Workstation Player - V17
- Image disque (ISO) : sparkylinux-6.4-x86_64-minimalcli.iso

## Utilisation de VMware et de l'image ISO linux 

A. Lancez VMware Workstation Player (logiciel)  

B. Sélectionnez **Create a New Virtual Machine** 

C. Placez le fichier `.iso` dans une repertoire connu : 

`C:\SVD\VM\ISO`

D. Indiquez le chemin d’accès de l’image iso comme indiqué sous l’image ci-dessous :

![install image disk](/Images/Install_ISO.jpg) 

E. Choisir un nom d'OS : `Linux - Debian 11.x` 

![OS name choice](/Images/OS_Choice.jpg) 

F. Nommez la machine virtuelle : `SparkyLinux-VosInitiales` 

G. Creez un disque virtuel -> capcité : **20GB** 

> remarque$$^1$$ : cocher **store virtual disk a single file**

![Virtual disk](/Images/VirtualDisk.jpg) 

> remarque$$^2$$ : ci-dessous, la configuration de la VM 

![Virtual disk](/Images/VM_Config.jpg) 

H. Lancez la machine virtuelle : **Play virtual machine** 

## Lancement de l'image ISO (Linux - Live CD) 

G. Lancement du live CD : 

<img width="1920" height="1041" alt="Capture d’écran 2025-09-18 153024" src="https://github.com/user-attachments/assets/b2d4a7d5-4c60-4c9a-8e23-97769159cf6c" />

Shell Linux : 

[Placer votre capture d'écran]() 

> **ATTENTION** : par défaut, le clavier est configuré est **Clavier Americain**

Q1. disposition du clavier américain ?

> QWERTY

Q2. disposition du clavier suisse-romand ?

> QWERTZ

Q3. disposition du le clavier français ? 

> AZERTY

H. Déplacez-vous à la **racine du système** en utilisant la commande suivante : `cd` 

Q4. Quelle est la commande complète ?

> cd /
I. Affichez le contenu de la racine avec la commande : `ls –l`	

<img width="1920" height="1041" alt="Capture d’écran 2025-09-18 155036" src="https://github.com/user-attachments/assets/ae7a91b8-9886-4c4e-81be-a33c2909efaf" />

Q5. Que signifie l'option `-l` avec la commande `ls` 

> L'option -l avec la commande ls signifie "long format"

Q6. Décrypter la ligne où se trouve le répertoire **home**    

<img width="1920" height="1041" alt="Capture d’écran 2025-09-18 155036 (1)" src="https://github.com/user-attachments/assets/6982e63a-451e-4f0d-add2-055b8bd2f7f8" />

> Sep 18 13:29 Date et heure de la dernière modification
> 60 c'est la taille du répertoire en octets
> 1 root root crée le lien entre le propriétaire et le groupe du répertoire
> d c'est le type de fichier d = directory
> rwxr-xr-x droits d'accès propriétaire
>home c'est le répertoire

J. Créez un répertoire de travail nommé « EMSY_VosInitiales» dans quel dossier racine allez-vous le placer (justifiez votre réponse) et quelle commande allez-vous utiliser. 

> cd /home/live
>  mkdir EMSY-SVD-NTN

Q7. Si vous créez un répertoire de travail (pour éditer/sauvegarder des fichiers), dans quelle **répertoire racine** vous vous placez ? 

> Dans notre nom d'utilisateur dans le home

Q8. Dans ce répertoire, créez un fichier texte que vous nommerez `TESTSLO_XXX_XXX` et éditez celui en écrivant un texte, exemple : "TP linux by XXX et XXX".
	Utiliser la commande `vi`

> vi TESTSLO_SVD_NTN

Q9. dans le répertoire `/home`, pouvez-vous éditez un fichier uniquement avec la commande `vi` 

> Non car nous ne somme pas dans le /home/live et nous n'avons donc pas l'option de faire cella.

Q10. Si vous éteignez la machine virtuelle et que vous la rallumez, est-ce que le répertoire créé ci-dessus existe toujours (justifiez votre réponse) ? 

> On est sur un CD virtuel donc on ne peut pas écrir desssus comme sur un vrais CD physique. 

L. Tapez la commande `ls -l /dev/sda` 

<img width="406" height="23" alt="Capture d’écran 2025-09-25 155625" src="https://github.com/user-attachments/assets/64f6d4f4-35a6-4de0-8325-2e33f16e6174" />

Q11. Que signifie **sda** ? 

> Disque dur (ou SSD) détecté en premier 

Q12. Décrypter la réponse après avoir taper la commande `ls -l /dev/sda` -> voir résultat point 13.

> b c'est le block
> rw c'est pour read et writ et le - veut dire qu'on a pas les permissions
> 1 c'est le nombre de lien vers le fichier
> root c'est le propriétaire du fichier
> disk c'est le groupe propriéaire du fichier
> 8 veut dire que c'est un périphérique SATA ou SCSI
> 0 indentifie le dispositif
> Sep 25 13:41 date et heure

Q13. Quelle est la taille de disque minimum recommandée pour insataller la distribution Sparky ? 

>2Go minimum recommander 

Q14. A quoi sert la partition swap ? Est-ce que ce principe existe sur les OS Microsoft Windows ?

>La partition swap est un espace sur le disque dur/SSD utilisé comme extension de la mémoire vive.
>Elle permet au système d’exploitation de gérer un manque de RAM / saturation de RAM et de mettre en veille prolongée.
>Non mais un principe équivalent existe. Sous Windows, il ne s’agit pas d’une partition dédiée mais d’un fichier d’échange appelé pagefile.sys

Q15. Quel format pourriez-vous utiliser pour la 3ème partiotion afin qu'elle soit également accessible depuis un OS Microsoft ? 

>W95 FAT32

Q16. Durant l'installation, on vous demande deux noms d'utilisateur. A quoi correspondent-ils ?

>Real user name c'est le nom de l'administrateur
>New user name c'est le nom d'utilisateur

Démarage système
<img width="317" height="107" alt="Capture d’écran 2025-10-02 162956" src="https://github.com/user-attachments/assets/33a90177-2f94-4fe5-891f-f09e7594b89c" />

Q17. À quoi sert "nano" ? 

Q18. Comment savoir si "git" est déjà installé ? 

Q19. Quelles commandes utilisez-vous pour l'installer ? 

Q20. Que veut dire "apt" ? 

Q21. ESt-ce que cette commande peut être utilisée sur toutes les distributions Linux ? 

Q22. Quel est le répertoire utilisateur ?

Q23. Quelles sont les commandes que vous allez utiliser

Q24. Qu'observez-vous dans votre répertoire ?

Q25. Quels sont les fichiers qui ont été générés ?

Q26. Que se pass-t-il ?

## Tips 

> $$Tips^1$$ : sortir de la VM -> appuyer simultanément sur `Ctrl` et `Alt` 

> $$Tips^2$$ : arrêter la VM proprement -> commande : `shutdown`

> $$Tips^3$$ : arrêter la VM pour cause de plantage -> commande : `halt` ou `poweroff`

> $$Tips^4$$ : [commande vi avec ses options](https://www.linuxtricks.fr/wiki/guide-de-sur-vi-utilisation-de-vi)

> $$Tips^5$$ : [éditer un fichier type markdown (.md)](https://ashki23.github.io/markdown-latex.html)
