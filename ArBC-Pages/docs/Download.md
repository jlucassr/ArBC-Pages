### Como Baixar e Executar

Para baixar a aplicação no seu computador basta clonar os repositórios:

```
$ git clone https://github.com/fga-eps-mds/2019.2-ArBC/
```

```
$ git clone https://github.com/fga-eps-mds/2019.2-ArBC-API/
```

Executar o comando build e up, sendo que o build só precisa ser executado na primeira vez. Primeiro executa na API:

```
$ sudo docker-compose -f local.yml build && sudo docker-compose -f local.yml up
```

```
$ sudo docker-compose build && sudo docker-compose up
```
