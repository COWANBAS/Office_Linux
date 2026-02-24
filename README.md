# INSTALAÇÃO

Recentemente migrei do windows para o linux, gostei bastante do sistema operacional novo porém estava faltando so uma coisa para ficar perfeito o MS Office, tenho varias planilhas e ficar sem mexer no Excel interfere meu trabalho passei horas pesquisando na internet e em forums como instalar no Linux depois de horas de pesquisa consegui finalmente rodar no linux via wine e quero compartilhar como instalar da forma mais filtrada possivel.

# Como funciona

Usaremos o WineHq para rodar o office no linux, o wine busca as apis que o aplicativo precisa do windows na sua distro linux fazendo assim com que seja totalmente possivel rodar aplicativos .exe no linux.

# WINEHQ

Primeiramente vamos baixar o WineHq, se estiver usando uma distro unbunto que nem a minha e bem simples basta inserir os comandos:

*sudo mkdir -pm755 /etc/apt/keyrings
wget -O - https://dl.winehq.org/wine-builds/winehq.key | sudo gpg --dearmor -o /etc/apt/keyrings/winehq-archive.key -*

*sudo wget -NP /etc/apt/sources.list.d/ https://dl.winehq.org/wine-builds/ubuntu/dists/questing/winehq-questing.sources*

*sudo apt update*

*sudo apt install --install-recommends winehq-stable*

Apos instalar o Wine acesse o terminal e digite "winecfg" vai abrir uma janela como se fossem as configurações do sistema operacional windows.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/91e430ab-2eca-440d-8913-52c4462cf40e" />
<br><br>
Navegue ate a aba "Bibliotecas" e instale as seguintes bibliotecas:
<br><br>

*msxml3*
*riched20*
*riched32*
*rpxrt4*


Rode o instalador do Office com o comando:

*wine (nome do executavel.exe)*

Agora e so aguardar enquanto ele ser instalado.

Para quem estiver tendo problemas com fontes recomendo que instale as fontes oficiais da microsoft executando os seguintes comandos:

*sudo apt update*
*sudo apt install ttf-mscorefonts-installer*
