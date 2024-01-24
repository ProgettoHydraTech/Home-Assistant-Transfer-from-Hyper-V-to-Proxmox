# Fare un Backup di Home assistant

Per saperne di più consultate [il nostro video](https://youtu.be/CnykIoaKyBc).

**Mi raccomando salvate il backup in un posto sicuro**

## Guida
[![forthebadge](https://forthebadge.com/images/badges/built-with-love.svg)](https://forthebadge.com)

1) Scarica Proxmox Virtual Enviroment Installer da [questo link](https://www.proxmox.com/en/downloads/proxmox-virtual-environment).
2) Flashalo su una USB con Balena Etcher o qualcosa di simile
3) Inserisci la USB dentro al Pc con montato un SSD/HDD vuoto dove andrete a installare proxmox

*Nota: se accendendo il PC non parte, correggi la sequenza di boot dal BIOS*

4) Segui tutti i passaggi per configuarare Proxmox(non li spiego qui) e finita l'installazione connettiti all'indirizzo ip che ti appare sullo schermo tramite browser in un altro pc.
5) Vai sulla Shell del server (ti si aprirà una finestra del Terminale)
6) Copia il link .qcow2 da [questa pagina web](https://www.home-assistant.io/installation/linux) con tasto destro -> copia indirizzo link
7) Nella Shell scrivete:

*Nota: non copiate i link degli esempi che possono essere versioni non aggiornate*

```bash 
wget IL_VOSTRO_LINK
```
_esempio: wget https://github.com/home-assistant/operating-system/releases/download/11.4/haos_ova-11.4.qcow2.xz_

Verrà scaricato un file con estensione .xz (xz è uno standard di compressione), per fare l'unzip del file digitate sempre nella Shell:

```bash
unxz IL_NOME_DEL_FILE 
```
_esempio: unxz haos_ova-11.4.qcow2.xz_

8) Scrivendo ls e pigiando poi invio vedrete il file nuovo senza l'estensione(.xz). seguite gli step nel video per la creazione della VM.
9) Dopo aver creato la VM SENZA AVERLA AVVIATA, digitate nella Shell:

```bash
qm importdisk VM_ID IL_NOME_DEL_FILE_CHE_AVETE_UNZIPPATO_PRIMA local-lvm
```
_esempio: qm importdisk haos_ova-11.4.qcow2 local-vm_

Poi seguite [il nostro video](https://youtu.be/CnykIoaKyBc) per maggiori istruzioni .
