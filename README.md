<h2>Do Windows ao Linux: As dores de cabeça que todo Dev tem...</h2>

<p>Alternar entre plataformas distintas pode gerar desconfortos no momento de uma transição.</p>

<h3>Objetivo</h3>
<p>Identificar desafios de um Dev PHP para utilizar e configurar o ambiente Linux.</p>

<h3>Labotarório DEBIAN 13</h3> 
<h4>Super usuário</h4>
<code>su -</code>
<h4>Adicionando o usuário atual ao grupo de supers</h4>
<code>usermod -aG sudo usuario</code></br>
<code>groups usuario</code></br>
<code>exit</code>
<h4>Atualização Inicial</h4>
<code>sudo apt update && sudo apt upgrade</code>
<h4>Adicionando fontes Microsoft</h4>
<code>sudo apt-add-repository contrib non-free</code></br>
<code>sudo nano /etc/apt/sources.list</code></br>
<code>sudo sed -i '/^deb / {/\bcontrib\b/! s/ main/ main contrib/}' /etc/apt/sources.list</code></br>
<code>sudo apt update</code></br>
<code>sudo apt install ttf-mscorefonts-installer</code>
<h4>Instalação do servidor Apache:</h4>
<code>sudo apt install apache2</code>
<h4>Instalação do PHP:</h4>
<code>sudo apt install php php-cli php-common php-mysql php-xml php-curl php-mbstring</code>
<h4>Instalação do banco de dados MariaDB:</h4>
<code>sudo apt install mariadb-server mariadb-client</code>
<h4>Configuração de segurança:</h4>
<code>sudo systemctl start mariadb</code></br>
<code>sudo systemctl enable mariadb</code></br>
<code>sudo systemctl status mariadb</code></br>
<code>sudo mariadb-secure-installation</code>
<h4>Instalação do Composer:</h4>
<code>sudo apt install composer</code>
<h4>Git</h4>
<code>sudo apt install git</code>
<h4>Node.js (para front-end integrado)</h4>
<code>sudo apt install nodejs npm</code>
<h4>Configuração do ambiente (htdocs):</h4>
<code>sudo chown -R $USER:www-data /var/www/html</code></br>
<code>sudo chmod -R 775 /var/www/html</code>
<h4>Instalação do PHPMyAdmin:</h4>
<code>sudo apt install phpmyadmin</code>
<h4>Durante a instalação:</h4>
<p>- Escolha o servidor web (Apache ou Nginx).</p>
<p>- Configure o banco de dados para phpMyAdmin.</p>
<p>- Defina uma senha para o usuário administrativo.</p>
<h4>Verifique se o link simbólico foi criado:</h4>
<code>sudo ln -s /usr/share/phpmyadmin /var/www/html/phpmyadmin</code>
<h4>Acesse o navegador:</h4>
<code>http://localhost/phpmyadmin</code>
<h4>Instalação Xdebug:</h4>
<code>sudo apt install php-xdebug</code>
<h4>Arquivo de configuração:</h4>
<code>sudo nano /etc/php/*/mods-available/xdebug.ini</code>
<h4>Adicione ou ajuste as linhas:</h4>
<code>zend_extension=xdebug.so</code></br>
<code>xdebug.mode=debug</code></br>
<code>xdebug.start_with_request=yes</code></br>
<code>xdebug.client_port=9003</code></br>
<code>xdebug.log=/var/log/xdebug.log</code>
<h4>Reinicie o servidor:</h4>
<code>sudo systemctl restart apache2</code>
<h4>Teste a instalação do PHP e do Xdebug:</h4>
<code>php -v</code>
<h4>Você deve obter algo como:</h4>
<code>with Xdebug v3.x.x</code>
<h4>Instalação do VS Code:</h4>
<code>wget -qO- https://code.visualstudio.com/sha/download?build=stable&os=linux-deb-x64 -O vscode.deb</code></br>
<code>sudo dpkg -i code_1.111.0-1772846623_amd64.deb</code></br>
<code>sudo apt --fix-broken install</code> 
