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
<code>sudo apt-add-repository contrib non-free</code>
<code>sudo nano /etc/apt/sources.list</code>
<code>sudo sed -i '/^deb / {/\bcontrib\b/! s/ main/ main contrib/}' /etc/apt/sources.list</code>
<code>sudo apt update</code>
<code>sudo apt install ttf-mscorefonts-installer</code>
<h4>Instalação do servidor Apache:</h4>
<code>sudo apt install apache2</code>
<h4>Instalação do PHP:</h4>
<code>sudo apt install php php-cli php-common php-mysql php-xml php-curl php-mbstring</code>
<h4>Instalação do banco de dados MariaDB:</h4>
<code>sudo apt install mariadb-server mariadb-client</code>
<h4>Configuração de segurança:</h4>
<code>sudo systemctl start mariadb</code>
<code>sudo systemctl enable mariadb</code>
<code>sudo systemctl status mariadb</code>
<code>sudo mariadb-secure-installation</code>
<h4>Instalação do Composer:</h4>
<code>sudo apt install composer</code>
<h4>Git</h4>
<code>sudo apt install git</code>
<h4>Node.js (para front-end integrado)</h4>
<code>sudo apt install nodejs npm</code>
<h4>Configuração do ambiente (htdocs):</h4>
<code>sudo chown -R $USER:www-data /var/www/html</code>
<code>sudo chmod -R 775 /var/www/html</code>
