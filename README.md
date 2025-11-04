# INSTALAÇÃO

Recentemente migrei do windows para o linux, gostei bastante do sistema operacional novo porém estava faltando so uma coisa para ficar perfeito o MS Office, tenho varias planilhas e ficar sem mexer no Excel interfere meu trabalho passei horas pesquisando na internet e em forums como instalar no Linux depois de horas de pesquisa consegui finalmente rodar no linux via wine e quero compartilhar como instalar da forma mais filtrada possivel.

# Como funciona

Usaremos o WineHq para rodar o office no linux, porém por padrão o Wine vem na versão 64 bits para instalar o Office teremos que aplicar uma via de configurações que deixem ele 32 Bits, pois o wine simula pastas do windows e como o Office geralmente e baixado na pasta (Program Files (x86)) se tentarmos instalar com o WineHq em 64 bits não vamos conseguir baixar.

# WINEHQ

Primeiramente vamos baixar o WineHq, se estiver usando uma distro unbunto que nem a minha e bem simples basta inserir os comandos:

- *sudo mkdir -pm755 /etc/apt/keyrings*
- *sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 76F1A20FF987672F*
- *sudo add-apt-repository 'deb https://dl.winehq.org/wine-builds/ubuntu/ jammy main'*
- *sudo apt update*
- *sudo apt install --install-recommends winehq-stable*

Apos instalar o Wine devemos instalar as depedencias necessaria, primeiramente vamos instalar o "WineTrickss"

- *sudo apt install winetricks*

Instale todas as depedencias necessarias:

- *winetricks vcrun2015*
- *winetricks corefonts*
- *winetricks dotnet48*
- *winetricks mfc42*
- *winetricks riched20*
- *winetricks msxml6*
- *winetricks usp10*

Apos isso confira se as bibliotecas *Msxml6*, *Riched20* e *Usp10* estão instaladas rodando o comando:

- *wine32 winecfg*

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ad6b4bf2-880c-4ede-87df-7bc7b76b98c0" />

Rode o instalador do Office com o comando:

- *wine (nome do executavel.exe)

Agora e so aguardar enquanto ele e instalado.


