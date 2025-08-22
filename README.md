# WINXProject - NGdevelopment
- Software Corporativo com objetivo de atender comércios com pontos de vendas, interface web para configuração de promções, devolução e controle de estoque.
- Oferecer confiabilidade, acessibilidade e redundança, garantindo a integridade dos dados e perfomance para o dia a dia.
- Interface customizavél de acordo com o cliente.
<br>
<hr>
<h1>Linguagens utilizadas</h1>
<b>Python;</b>
<br>
<b>PHP;</b>
<br>
<b>JavaScript;</b>
<br>
<br>
<h1>Frameworks utilizadas</h1>
<b>Django;</b>
<br>
<b>Tkinter;</b>
<br>
<b>Laravel;</b>
<br>
<b>Vue.js;</b>
<br>
<b>ReactNative;</b>
<hr>
<h1>Configurando o Git</h1>
🔑 Gerando a chave SSH
<hr>
No seu terminal do WSL, digite:

    ssh-keygen -t ed25519 -C "seu_email_do_github@example.com"


Se der erro dizendo que não suporta ed25519, use:

    ssh-keygen -t rsa -b 4096 -C "seu_email_do_github@example.com"


Ele vai perguntar onde salvar. Pressione Enter para o caminho padrão:

    /home/seu_usuario/.ssh/id_ed25519


Se quiser, defina uma senha (ou só aperte Enter para deixar sem).

<hr>

🔐 Iniciando o agente SSH e adicionando a chave

Inicie o agente:

    eval "$(ssh-agent -s)"


Adicione sua chave ao agente:

    ssh-add ~/.ssh/id_ed25519

📋 Copiando a chave pública

Agora copie o conteúdo da chave pública:

    cat ~/.ssh/id_ed25519.pub


Copie a linha inteira que começa com ssh-ed25519 ou ssh-rsa.

🔗 Adicionando ao GitHub

Vá no GitHub → Settings → SSH and GPG keys.

    Clique em New SSH key.

Cole a chave pública e dê um nome (ex: WSL).

🧪 Testando a conexão

Rode:

    ssh -T git@github.com


Se tudo deu certo, vai aparecer:

    Hi NOME_DE_USUARIO! You've successfully authenticated...

<hr>

#🐧 Tutorial de Instalação e Configuração do WSL com Ubuntu
1. Windows Subsystem for Linux (WSL)
🔹 Pré-requisitos

Abra o PowerShell como Administrador no Windows.

Instale o Ubuntu no WSL:

    wsl --install -d Ubuntu


# Defina o Ubuntu como distribuição padrão e configure o usuário root (opcional):

    wsl --set-default Ubuntu
    wsl -d Ubuntu -u root
            ou
    wsl --set-user root
            ou
    ubuntu config --default-user root
            ou
    ubuntu2004 config --default-user root


#Configurar usuário root como padrão (se preferir):
#Abra o Ubuntu (22.04, por exemplo) e edite o arquivo /etc/wsl.conf:

    sudo nano /etc/wsl.conf


Adicione o conteúdo:

    [user]
    default=root


Salve, feche e depois reinicie o WSL:

    wsl --shutdown


Reinicie o computador.

2. Configuração do Ubuntu no WSL
Passos principais:

Abra o Ubuntu pelo Menu Iniciar e confirme se está como root:

whoami


→ deve aparecer root (se configurado como padrão).

#📦 Atualizar pacotes

Atualize a lista de pacotes:

    apt update && apt upgrade -y

#🐳 Instalar Docker

Instale o Docker:

    apt install -y docker.io
    systemctl enable docker
    systemctl start docker


Teste com:

    docker --version

#🐙 Instalar Git

Instale o Git:

    apt install -y git
    git --version

#🟩 Instalar Node.js (via NVM)

Instale o NVM (Node Version Manager):

    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
    source ~/.bashrc


Instale a versão LTS do Node.js:

    export NVM_DIR="$HOME/.nvm"
    [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"

    nvm install --lts
    node -v
    npm -v

#🐍 Instalar Python

Instale o Python + Pip:

    apt install -y python3 python3-pip
    python3 --version
    pip3 --version

#🐘 Instalar PHP

Instale o PHP e extensões comuns:

    apt install -y php php-cli php-fpm php-mbstring php-xml php-curl php-zip php-gd php-mysql php-pgsql
    php -v


    Adicione o PHP ao PATH (se necessário):

    echo 'export PATH=$PATH:/usr/bin/php' >> ~/.bashrc
    source ~/.bashrc

<hr>
✅ Pronto! Seu ambiente WSL (Ubuntu) agora tem:

Docker

Git

Node.js (via NVM)

Python + Pip

PHP com extensões populares