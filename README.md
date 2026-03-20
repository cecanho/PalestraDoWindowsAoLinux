<h3>Do Windows ao Linux: As dores de cabeça que todo Dev tem...</h3>

<p>Alternar entre plataformas distintas pode gerar desconfortos no momento de uma transição.</p>

<h4>Objetivo</h4>
<p>Identificar desafios de um Dev PHP para utilizar e configurar o ambiente Linux.</p>

<h4>Labotarório DEBIAN 13 - Super usuário</h4>
<code>su -</code>
<h4>Adicionando o usuário atual ao grupo de supers</h4>
<code>usermod -aG sudo usuario
groups usuario
exit</code>
<h4>Atualização Inicial</h4>
<code>sudo apt update && sudo apt upgrade</code>
<h4>Adicionando fontes Microsoft</h4>
<code>sudo apt-add-repository contrib non-free
sudo nano /etc/apt/sources.list
sudo sed -i '/^deb / {/\bcontrib\b/! s/ main/ main contrib/}' /etc/apt/sources.list
sudo apt update
sudo apt install ttf-mscorefonts-installer</code>
<h4>Instalação do servidor Apache:</h4>
<code>sudo apt install apache2</code>

Instalação do PHP:
sudo apt install php php-cli php-common php-mysql php-xml php-curl php-mbstring -y
