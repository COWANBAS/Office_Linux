# DISCLAIMER
Recentemente migrei do windows para o linux, gostei bastante do sistema operacional novo porém estava faltando so uma coisa para ficar perfeito o MS Office, tenho varias planilhas e ficar sem mexer no Excel interfere meu trabalho passei um tempo pesquisando na internet e em forums como instalar no Linux depois de algums minutos de pesquisa consegui finalmente rodar o office no linux via wine e quero compartilhar como instalar da forma mais simples e filtrada possivel,usaremos o Wine para rodar o office no linux, o wine busca as apis que o aplicativo precisa do windows na sua distro linux fazendo assim com que seja totalmente possivel rodar aplicativos .exe no linux.
# WINE
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
Apos instalar o Wine acesse o terminal e digite (winecfg) vai abrir uma janela como se fosse as configurações do sistema windows.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c4dac923-fc75-44fd-9f9d-65b656e922a4" />

<br><br>
Navegue até a aba (Bibliotecas) e instale as seguintes bibliotecas:
<br><br>

vcrun2005
&nbsp;
vcrun2008
&nbsp;
vcrun2010
&nbsp;
msxml3
&nbsp;
msxml6
&nbsp;
riched20
&nbsp;
riched32
&nbsp;
gdiplus
&nbsp;
usp10
&nbsp;
ole32
&nbsp;
oleaut32
&nbsp;
oleacc
&nbsp;
atmlib
&nbsp;
<br><br>
Rode o instalador do Office via wine e o instale normalmente, para quem estiver tendo problemas com fontes apos instalar recomendo que instale as fontes oficiais da Microsoft executando o comando abaixo.
<br><br>

```bash
sudo apt update
```
```bash
sudo apt install ttf-mscorefonts-installer
```
# WINETRICKS
Instale o Winetricks. para baixar mais algumas dependências e garantir a total funcionalidade do Excel

```bash
sudo apt install winetricks
```
Agora baixe mais algumas dependências e garantir a total funcionalidade do Excel

```bash
winetricks corefonts
winetricks vcrun2005 vcrun2008
winetricks riched20 riched30 msxml6
winetricks dotnet20
winetricks dotnet30
winetricks dotnet35
winetricks dotnet40
```
