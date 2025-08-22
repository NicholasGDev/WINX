
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