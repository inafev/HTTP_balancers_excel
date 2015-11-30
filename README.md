# HTTP_balancers_excel
Configuration example of hardware HTTP balancers with non-root ports for Apache

Nota: en rojo los puertos para tráfico SSL de Apache que resultan prescindibles. Como los nuevos balanceadores hardware admiten certificados y tráfico SSL, no son necesarias las instancias SSL de Apache. Redirigimos/Balanceamos los puertos 443 de los balanceadores hardware hacia los puertos NO SSL de Apache. De esta forma liberamos de CPU las VM con Apache al no tener que gestionar tráfico encriptado (el más costoso a nivel de CPU).

Apache SSL ports highlighted in red should not be set up. Default 443 SSL ports reachable from Internet run on hardware HTTP balancers, balancing HTTP and HTTP-SSL traffic onto our "HTTP-only" Apache servers (unreachable from Internet, no SSL traffic required internally). Also take into account that enabling SSL in our Apaches would require a large amount of VM CPU usage.
