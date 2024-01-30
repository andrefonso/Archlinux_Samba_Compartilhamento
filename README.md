# archlinux_file_sharing
Tutorial para configuração do Samba e compartilhamento de arquivos no Arch Linux
---

### PASSOS PARA CONFIGURAR O SAMBA NO ARCH LINUX: 

1- Instale o samba com o seguinte comando:

``sudo pacman -S samba``

2- Crie o arquivo **smb.conf** utilizando o Nano com o nome de no diretório _/etc/samba/_ colando dentro dele o conteúdo contido no arquivo **smb.txt** disponível nesse repositório.

3- Altere o proprietário do arquivo _smb.conf_ para **andre** usando o seguinte comando:</br>
``sudo chown andre /etc/samba/smb.conf``

4- Altere o grupo do arquivo _smb.conf_ para **andre** usando o seguinte comando:</br>
``sudo chown :andre /etc/samba/smb.conf``

5- Altere as permissões do arquivo _smb.conf_ usando o seguinte comando:</br>
``sudo chmod 777 /etc/samba/smb.conf``

6- Crie seu usário e senha para o samba com o comando:

``sudo smbpasswd -a andre``

7- Habilite a inicialização automática do serviço com o seguinte comando:

``sudo systemctl enable samba smbd nmbd``

 |Obs. caso o comando acima mostre este aviso: **Failed to enable unit: Unit file smbd.service does not exist.**

8- Use estes comando:</br>
```
sudo systemctl enable smb.service
sudo systemctl restart smb nmb
sudo systemctl enable samba smbd nmbd
```
9- Reinicie o pc.

10- Verifique se o samba está instalado e rodando:

``sudo smbstatus``

