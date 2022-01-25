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


## Différence avec ARM


## Sur une boucle for


## Contre le patching



