# archlinux_file_sharing
Tutorial para configuração do Samba e compartilhamento de arquivos no Arch Linux
---

### PASSOS PARA CONFIGURAR O SAMBA NO ARCH LINUX: 

1- Instale o samba com o seguinte comando:

``sudo pacman -S samba``

2- Crie o arquivo **smb.conf** no diretório _/etc/samba/_ colando dentro dele o conteúdo contido no arquivo **smb.txt** disponível nesse repositório

3- Crie seu usário e senha para o samba com o comando:

``sudo smbpasswd -a andre``


4- Habilite a inicialização automática do serviço com o seguinte comando:

``sudo systemctl enable samba smbd nmbd``

 |Obs. caso o comando acima mostre este aviso: **Failed to enable unit: Unit file smbd.service does not exist.**

Use este comando:</br>

``sudo systemctl enable smb.service``

5- Reinicie o pc.

6- Verifique se o samba está instalado e rodando:

``sudo smbstatus``

