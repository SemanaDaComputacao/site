Instalação
==========
Esse projeto usa o [Jekyll](https://jekyllrb.com/) como gerenciador de site estático ([instruções de instalação](https://jekyllrb.com/docs/installation/)). O Bulma está copiado na pasta `_sass` para evitar baixar dependências via npm.

Para instalar, basta rodar o comando:

```
bundle install
```

Rodando localmente
------------------
```
bundle exec jekyll serve
# ou
bundle exec jekyll serve --livereload
```

Deploy
======
O site é hospedado em um site com subcaminho, do tipo `site.com/example`, enquanto no ambiente de desenvolvimento ele fica sem o subcaminho (`localhost/`).

O subcaminho é especificado em `baseurl`, no arquivo `_config.yml`. Os links precisam fazer referência a tal subcaminho, se existir, por isso sempre precedemos os links com `{{ site.baseurl }}`.

Há dois arquivos de configuração: `_config.yml` e `_config-deploy.yml`. Por padrão, é usado o `_config.yml`, mas para hospedar o site num sub-caminho, podemos sobrescrever a variável `baseurl` com o `_config-deploy.yml`. Para fazer o build do deployment, podemos fazer assim:

```
bundle exec jekyll build --config _config.yml _config-deploy.yml
```
