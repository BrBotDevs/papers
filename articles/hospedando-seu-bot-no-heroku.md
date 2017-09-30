# Hospedando seu bot no Heroku

Depois de ter criado [seu primeiro bot](https://tableless.com.br/seu-primeiro-bot-para-o-telegram/) e ter criado alguns comandos customizados, ja deve ter percebido que ele so fica disponivel enquanto estiver com ele rodando no seu terminal. Então eu vou te mostrar como hospedar o seu bot no Heroku.

# Sobre o Heroku

O [Heroku](https://www.heroku.com/home) e uma das melhores e mais populares opções de plataforma como serviço(Paas), ela suporta várias aplicações em diversas linguagens, dentre elas o NodeJS. Existem planos gratuitos e alguns pagos, coisa de 7USD que te garante diversos benefícios, mas não vai ser preciso, a versão gratuita vai servir muito bem.

# Como funciona

O Heroku não disponibiliza o acesso a máquina, ele vai disponibilizar algumas opções como Heroku CLI, GitHub e Dropbox para fazer o deploy da sua aplicação em seus servidores. Nesse caso vamos utilizar o código do nosso projeto que esta no [GitHub](https://github.com/rafaelvicio/primeiro-bot).

# Vamos la

Apos fazer login no [Dashboard](https://dashboard.heroku.com/apps) do Heroku clique no botão `New` localizado no canto superior direito, clique em `Create new app`.

![Dashboard](http://i.imgur.com/VJY9uR7.png)

Escolha um nome para a sua aplicação, ela não deve ter caracteres em maiúsculo. A nossa vai se chamar `primeirobot`. Também escolha uma região, a minha vai ser `United States`. Depois clique em `Create App`.

![Dashboard](http://i.imgur.com/iPRRyht.png)

Agora você vai precisar escolher o `Deploy method`, nesse caso vamos escolher o GitHub. Provavelmente você vai precisar informar a sua conta do GitHub e autorizar a integração das duas ferramentas.

Depois de escolher o GitHub, você vai precisar informar o nome do repositório do GitHub, vou escolher o [Primeiro Bot](https://github.com/rafaelvicio/primeiro-bot) e clicar em `Connect`.

![Dashboard](http://i.imgur.com/qak3DQG.png)

Depois, você vai precisar configurar o `Automatic deploys`, isso permite que a cada novo commit no projeto o mesmo seja atualizado no servidor do Heroku. Vamos escolher aqui a branch master para ajudar.

![Dashboard](http://i.imgur.com/MZo6Gmt.png)

Agora, escolher em `Manual deploy` uma branch para realizar o primeiro deploy da aplicação no servidor. Esse processo pode levar alguns minutos, voce verá uma pequena caixa de log do processo.

# Configuração

Agora, para iniciar a aplicação você vai precisar realizar um pequeno ajuste. Abra o seu código e faça uma alteração no seu `package.json`. Adicione o seguinte script `"start": "node index"`. Faça o commit dessa alteração no repositório do GitHub.

Agora volte no Heroku e no menu central superior, clique em `Resources`. Agora configure um Dyno clicando em edit e ative o Dyno que já vem configurado como `npm start`(aquele que acabamos de configurar no package.json).

![Dashboard](http://i.imgur.com/MvHGC9V.png)

Agora clique em `Confirm` e aguarde.

Você pode verificar os logs no menu do canto superior direito clicando em `More -> Views logs`. Você vai poder ver todo o processo. Pronto, sua aplicação está rodando no Heroku.

Depois de realizar qualquer commit no repositório do GitHub, o servidor do Heroku vai se atualizar com com o repositório.
