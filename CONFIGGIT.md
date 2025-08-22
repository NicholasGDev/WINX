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