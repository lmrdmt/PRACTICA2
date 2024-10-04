# Práctica 2

```markdown
# Práctica 2

## Comproba que tes a imaxe httpd

```bash
docker images
```
 
Se non tes a imaxe, descárgaa:

```bash
docker pull httpd
```

## Crea un contedor de nome 'asir_httpd'.

```bash
docker create --name asir_httpd -p 8080:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/httpd
```

## Mapea o porto 80 do contedor co 8080 da túa máquina.

Utiliza un bind mount para que o directorio do Apache2 `htdocs` estea montado nun directorio da túa elección:

```bash
docker create --name asir_httpd -p 8080:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/httpd
```

## Mostra unha páxina HTML aloxada en Apache2 dende o teu navegador.

Executa o contedor con:

```bash
docker start asir_httpd
```

A continuación, abre o teu navegador e na barra de URL escribe: **localhost:8080**

## Crea un contedor 'asir_web1' que use este mesmo directorio para 'htdocs' e o porto 8000.

```bash
docker create --name asir_web1 -p 8000:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/httpd
```

## Crea outro contedor 'asir_web2' co mesmo directorio e outro porto, como o 8090.

```bash
docker create --name asir_web2 -p 8090:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/httpd
```

## Comproba que os dous servidores mostran a mesma páxina.

Inicia os contedores con:

```bash
docker start asir_web1
docker start asir_web2
```

Abre o teu navegador e na barra de URL escribe `localhost:8090` para comprobar `asir_web2`, e logo fai o mesmo con `asir_web1` escribindo `localhost:8000`.
```



