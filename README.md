# PRACTICA2


    ##Comproba que a tes a imaxe httpd##
    ´´´docker images´´
    ---
    se non temos a imaxe 
    ´´´docker pull httpd´´
    ---
    ##Crea un contenedor de nome 'asir_httpd'.##
    ´´´docker create --name asir_httpd -p 8080:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/httpd´´´
    ---
    ##Mapea o porto 80 do contenedor có 8080 da túa máquina.
    Utiliza bind mount para que o directorio do apache2 'htdocs' estea montado nun directorio da túa elección.##

        Utiliza -v "$PWD"/htdocs:/usr/local/apache2/htdocs/

 ´´´docker create --name asir_httpd -p 8080:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/httpd´´´

    ##Mostra unha páxina html aloxada no apache2 dende o teu navegador.##
    Executamos o repositorio cun " docker start "nome_do_repositorio ".
    A continuacón abrimos o noso navegador en na barra de URLS escribimos: **localhost:8080** 
    
    ##Crea un contenedor 'asir_web1' que use este mesmo directorio para 'htdocs' e o puerto 8000##
    
     ´´´docker create --name asir_httpd -p 8000:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/httpd´´´

    
    ##Crea outro contenedor 'asir_web2' có el mesmo directorio e otro puerto, como o 8090.##
     ´´´docker create --name asir_httpd -p 8090:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/httpd´´´

    ##Comproba que los dous servidores mostran a mesma páxina##
    Iniciamos os repos con docker start "nome do repo"
    navegador e na barra de URL escribimos localhost:8090.
    Para comprobar asir_web1 o iniciaremos eh faremos o mesmo que o apartado anterior pero co localhost:8000

   


