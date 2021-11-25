# Git e GitHub

Guia prático para iniciantes

## Instalação

### Linux

```
sudo apt-get install git-all
```
## Configuração

Após a instalação o Git vai criar o arquivo `.gitconfig` na pasta do usuário `/home/meu-usuario`.\
Obs: ele é um arquivo oculto por padrão.

### Identidade

Agora vamos vincular um nome de usuário e email nas configurações do Git. Esses dados devem ser os mesmo que vamos cadastrar no GitHub
Obs: Caso já tenha conta é só usar seu usuário e email já cadastrado

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

## Adicionando uma chave SSH

Neste passo, vamos aprender como adicionar uma chave SSH à sua conta do GitHub , o que vai te permitir fazer pushes e pulls sem ter que ficar digitando usuário e senha toda vez.
Dê uma olhada na documentação oficial do GitHub Sobre isso.

https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account


