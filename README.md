# DISCLAIMER
Recentemente migrei do windows para o linux, gostei bastante do sistema operacional novo porém estava faltando so uma coisa para ficar perfeito o MS Office, tenho varias planilhas e ficar sem mexer no Excel interfere meu trabalho passei um tempo pesquisando na internet e em forums como instalar no Linux depois de algums minutos de pesquisa consegui finalmente rodar o office no linux via wine e quero compartilhar como instalar da forma mais simples e filtrada possivel,usaremos o Wine para rodar o office no linux, o wine busca as apis que o aplicativo precisa do windows na sua distro linux fazendo assim com que seja totalmente possivel rodar aplicativos .exe no linux.
# INSTALAÇÃO
Primeiramente vamos baixar o Wine rodando os comandos a seguir, vou fazer o tutorial de instalação com base na minha distro que e o ubuntu.

```bash
sudo mkdir -pm755 /etc/apt/keyrings
wget -O - https://dl.winehq.org/wine-builds/winehq.key | sudo gpg --dearmor -o /etc/apt/keyrings/winehq-archive.key -
```

```bash
sudo wget -NP /etc/apt/sources.list.d/ https://dl.winehq.org/wine-builds/ubuntu/dists/questing/winehq-questing.sources
```

```bash
sudo apt update
```

```bash
sudo apt install --install-recommends winehq-stable
```

Apos instalar o Wine acesse o terminal e digite "winecfg" vai abrir uma janela como se fosse as configurações do sistema windows.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/91e430ab-2eca-440d-8913-52c4462cf40e" />
<br><br>
Navegue até a aba "Bibliotecas" e instale as seguintes bibliotecas:
<br><br>
msxml3
&nbsp;
riched20
&nbsp;
riched32
&nbsp;
rpxrt4
<br><br>
Rode o instalador do Office e aguardeenquanto ele ser instalado, para quem estiver tendo problemas com fontes recomendo que instale as fontes oficiais da microsoft executando os seguintes comandos:
<br><br>

```bash
sudo apt update
```
```bash
sudo apt install ttf-mscorefonts-installer
```
