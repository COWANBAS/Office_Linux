# Office_Linux

Recentemente migrei do windows para o linux, gostei bastante do sistema operacional novo porém estava faltando so uma coisa para ficar perfeito o MS Office, tenho varias planilhas e ficar sem mexer no Excel interfere meu trabalho passei horas pesquisando na internet e em forums como instalar no Linux depois de horas tentando instalar consegui finalmente rodar no linux via wine e quero compartilhar como instalar da forma mais filtrada possivel.

# Como funciona

Usaremos o WineHq para rodar o office no linux, porém por padrão o Wine vem na versão 64 bits para instalar o Office teremos que aplicar uma via de configurações que deixem ele 32 Bits, pois o wine simula pastas do windows e como o Office geralmente e baixado na pasta (Program Files (x86)) se tentarmos instalar com o WineHq em 64 bits não vamos conseguir baixar.

# WINEHQ

Primeiramente vamos baixar o WineHq, se estiver usando uma distro unbunto que nem eu e bem simples basta inserir os comandos.

- *sudo mkdir -pm755 /etc/apt/keyrings*
- *wget -O - https://dl.winehq.org/wine-builds/winehq.key | sudo gpg --dearmor -o /etc/apt/keyrings/winehq-archive.key -*
- *sudo apt install --install-recommends winehq-stable*

Apos instalar o Wine devemos instalar as depedencias necessaria, primeiramente vamos ativar o suporte 32 bits para o wine digitando o comando

- *sudo dpkg --add-architecture i386*
