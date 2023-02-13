Rapport d'analyse forensique sur la clé USB trouvée

Analyse effectuée le 13/02/2023 par Joé BIAVA

1ère étape : Récupérer des informations sur l'image

En tout premier, le checksum de l'image "USB_IMAGE" a été vérifié, grâce à l'outil sha256sum. Le résultat a été comparé au checksum donné. Les deux concordent, ce qui garantit l'intégrité des données. 
Des informations ont été récupérées  grâce à des outils tels xxd ou minfo (voir dossier "img), comme le système de fichier et le type d'image ou même les messages d'erreur lors du boot.
L'outil testdisk a permis de récupérer également quelques informations sur la composition de cette image.
L'outil exiftool a permis de connaître également la taille de l'image.
Enfin, les outils foremost et binwalk ont permis d'identifier que des fichiers pourraient être exploités.

2ème étape : Récupération des fichiers

Un outil appelé "photorec" permet de récupérer des fichiers supprimés et de les intégrer dans un répertoire afin de les consulter. Cela a permis de récupérer plusieurs fichiers, dont des .png, un .ini, un .xml et des .jpeg.
La consultation de deux de ces documents identifie la preuve recherchée lors de cette étape, c'est à dire une photo d'un tableau blanc sur lequel est écrit "bosch{1MAG3}". L'analyse a ainsi permis de récupérer une preuve d'identification.
Cette récupération a également permis d'identifier dans un fichier .ini un chemin nommé "secret.png" qui pourrait attirer l'attention.

Les fichiers correspondant à la preuve se nomment "f0016520.png" et "f0040392.png" et la preuve a été enregistrée dans le dossier "TP01/img" sous le nom flag.png.

Signature :
JB

Fait le :
13/02/2023

à :
16h10
