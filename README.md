Giropops Senha é um gerador de senha escrito em Python.

Para rodar a aplicação localmente, é necessário um Redis acessível pela aplicação.


(Exemplo de flow para expor a aplicação localmente na porta 99990
```
docker build -t giropops-senha .
docker run -d --name redis redis
REDIS_HOST=`docker inspect --format '{{ .NetworkSettings.IPAddress }}' redis`
docker run -d -p 9999:5000 --env REDIS_HOST=$REDIS_HOST --name giropops-senha giropops-senha
curl localhost:9999
```
