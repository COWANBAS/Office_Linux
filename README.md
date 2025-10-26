# Office_Linux

Recentemente migrei do windows para o linux, gostei bastante do sistema operacional novo porém estava faltando so uma coisa para ficar perfeito o MS Office, tenho varias planilhas e ficar sem mexer no Excel interfere meu trabalho passei horas pesquisando na internet e em forums como instalar no Linux depois de horas tentando instalar consegui finalmente rodar no linux via wine e quero compartilhar como instalar da forma mais filtrada possivel.

# Como funciona

Usaremos o WineHq para rodar o office no linux, porém por padrão o Wine vem na versão 64 bits para instalar o Office teremos que aplicar uma via de configurações que deixem ele 32 Bits, pois o wine simula pastas do windows e como o Office geralmente e baixado na pasta (Program Files (x86)) se tentarmos instalar com o WineHq em 64 bits não vamos conseguir baixar.

# WINEHQ

Primeiramente vamos baixar o WineHq, se estiver usando uma distro unbunto que nem eu e bem simples basta inserir os comandos:

- *sudo mkdir -pm755 /etc/apt/keyrings*
- *wget -O - https://dl.winehq.org/wine-builds/winehq.key | sudo gpg --dearmor -o /etc/apt/keyrings/winehq-archive.key -*
- *sudo apt install --install-recommends winehq-stable*

Apos instalar o Wine devemos instalar as depedencias necessaria, primeiramente vamos ativar o suporte 32 bits para o wine digitando o comando:

- *sudo dpkg --add-architecture i386*

Depois de rodar esse comando instalaremos o Winetricks para rodar a instalação dos pacotes necessarios para o Office:

- *sudo apt install winetricks*

Apos baixar vamos configurar o prefix do wine 32 bits no linux para isso instale os arquivos msi da Gecko nesse link: https://gitlab.winehq.org/wine/wine/-/wikis/Gecko e os coloque na pasta *~/.cache/wine.*

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/123c89b4-01ce-4ffd-b8c8-8ab3d2895211" />

Depois disso coloque no terminal o seguinte comando para criar o prefixo 32 bits do wine:

- *WINEPREFIX='~/.wine32' WINEARCH='win32' wine 'wineboot'*

  Lembrando de substituir o ~/ pelo seu usuario

Navegue ate a pasta */etc/skel/* e ache o arquivo *.bashrc* copie ele e cole na sua pasta de usuario, abra ele e no final do arquivo coloque os  comandos:

- *alias wine32="WINEPREFIX='~/.wine32'"*

- *WINEARCH=win32 winecfg*

Exporte os prefixos 32 bits no terminal com:

- *export WINEPREFIX=~/.wine32*
