# Git e GitHub

Guia prático para iniciantes

## Instalação

### Linux

```
sudo apt-get install git-all
```
## Configuração

Após a instalação o Git vai criar o arquivo `.gitconfig` na pasta do usuário `/home/meu-usuario`.\
_**Obs: ele é um arquivo oculto por padrão.**_

### Identidade

Agora vamos vincular um nome de usuário e email nas configurações do Git. Esses dados devem ser os mesmo que vamos cadastrar no GitHub\
_**Obs: Caso já tenha conta é só usar seu usuário e email já cadastrado**_

```
git config --global user.name "seunome"
git config --global user.email seuemail@exemplo.br
```

### Editor

Vamos definir o Vs Code como o editor padrão do arquico de configuração do Git, `.gitconfig`.

```
git config --global core.editor "code --wait"
```

### Testando a instalação e configuração

Vamos testar a instalação do git com o comando abaixo. Se tudo estiver certo seu terminal deve mostrar algo pararecido com\
`git version 2.x.x`

```
 git --version
```

Agora vamos testar se a configuração do seu usuário e senha está correta. Se tudo estiver certo vc deve conseguir ver o usuário e senha que inseriu anteriormente.\
`user.name=seunome`\
`user.email=seuemail@exemplo.br`

Digite o comando abaixo:
```
git config --list
```

## Criando uma conta no GitHub
Crie uma conta no GitHub com o seu email. https://github.com/

## Adicionando uma chave SSH

Neste passo, vamos aprender como adicionar uma chave SSH à sua conta do GitHub , o que vai te permitir fazer pushes e pulls sem ter que ficar digitando usuário e senha toda vez.
Dê uma olhada na documentação oficial do GitHub para informações mais detalhadas.

https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

### Gerando uma nova chave SSH

O ideal é ter uma chave para cada máquina que você for usar para commitar na sua conta do GitHub.

_**ATENÇÃO: COLOQUE SEU EMAIL DO GITHUB NO CÓDIGO ABAIXO!!!**_

```
ssh-keygen -t rsa -b 4096 -C "seuemail@gmail.com"
```

irá aparecer escrito no terminal\
`Enter a file in which to save the key (/home/you/.ssh/id_rsa):` \
quando isso acontecer pressione _**Enter**_ para aceitar a localização padrão.

Agora você deve digitar uma senha segura.

```
Enter passphrase (empty for no passphrase): [senhasegura]
Enter same passphrase again: [senhasegura]
```

### Adicionando sua chave SSH ao ssh-agent

Primeiro você deve iniciar o ssh-agent em background:

```
eval "$(ssh-agent -s)"
```
Agora você deve adicionar sua chave privada SSH ao ssh-agent . Para isso execute o comando abaixo no terminal:

```
ssh-add ~/.ssh/id_rsa
```

> Caso encontre o erro `WARNING: UNPROTECTED PRIVATE KEY FILE!` redefina as permissões da chave para o padrão com o comando a seguir: `sudo chmod 600 ~/.ssh/id_rsa; sudo chmod 600 ~/.ssh/id_rsa.pub`

### Adicionando a chave SSH a sua conta do GitHub

Ao execultar o comando abaixo o terminal exibirá sua chave SSH. Você deve copiá-la. \

```
cat ~/.ssh/id_rsa.pub
```
Nem todos os teminais aceitam o `Ctrl + c` então tente selecionar a chave e clique com o botão direito do mouse, depois em copiar. Caso o seu terminal não mostre  opção de copiar com o botão direito do mouse tente `Ctrl + Shif + C`. Pra ter certeza que a cave foi copiada, cole-a em qualquer editor de texto .

Entre no seu GitHub e siga os passos abaixo:
- No canto superior direito do GitHub , clique na sua foto de perfil e clique em **Settings** ;
- Na barra lateral esquerda, clique em **SSH and GPG keys** ;
- Clique em **New SSH key** ou Add SSH key ;
- No campo **Título** , adicione um descrição para a nova chave, pode ser o nome do seu computador;
- Cole sua chave dentro do campo **Key** ;
- Clique em **Add SSH key** ;
- Caso seja solicitado, confirme sua senha do Github.

## Seu repositório

Navegue até a pasta do seu repositório e siga os seguintes passos:
- Digite o seguinte comando `git init`, pronto o git já foi iniciado na pasta atual.
- Crie um arquivo README.md para inserir as informações sobre o projeto que tem na pasta.
- Adicione o arquivo ao stage com o comando `git add .` ou `git add <nome-do-arquivo>`.
- Insira um breve comentário informando do que se trata o arquivo usando `git commit -m "Iniciando o projeto"`
