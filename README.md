# TD3 Binwalk

## À la recherche de tux
J'utilise successivement binwalk et dd après avoir installé la machine : 
```user@optiplex-1503:~/Documents/SecuEmbarque/binwalk$ binwalk vmlinuz-qemu-arm-2.6.20 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             Linux kernel ARM boot executable zImage (little-endian)
12720         0x31B0          gzip compressed data, maximum compression, from Unix, last modified: 2007-05-09 06:03:48

```
Après 3 fois, j'obtiens l'image de tux : 

```
2984412       0x2D89DC        ASCII cpio archive (SVR4 with no CRC), file name: "/usr/local/share/directfb-examples/tux.png", file name length: "0x0000002B", file size: "0x00006050"
```

## Modification de tux
J'ai ouvert le fichier de tux dans un éditeur d'image et j'ai modifié quelques paramètres comme le contraste. 
Ensuite, je voulais recréer la machine virtuelle en faisant les opérations inverses. Après plusieurs essais, j'ai trouvé la commande suivante qui me permettait d'extraire plus rapidement.
```binwalk -e -M -r --directory=. vmlinuz-qemu-arm-2.6.20
```
Voici ensuite les commandes que j'ai utilisées pour faire les "remontages" : 
```
cd _vmlinuz-qemu-arm-2.6.20-0.extracted/_31B0.extracted/_E7E0.extracted/cpio-root/
find . | cpio -o -H newc >> ./../../bob.cpio
cd ../../
gzip _31B0.extracted/E7E0
mv E7E0.gz E7E0
dd if=E7E0 of=31B0 bs=1 seek=59360 conv=notrunc
gzip 31B0
mv 31B0.gz 31B0
dd if=31B0 of=vmlinuz-qemu-arm-2.6.20 bs=1 seek=12720 conv=notrunc
```

Après comparaisons, l'image de base et l'image recrée sont bien les mêmes quand on les observe avec binwalk (hormis les dates évidemment) : 

## Différence avec ARM


## Sur une boucle for


## Contre le patching



