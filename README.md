# escalabilidad-practica-1-sem-3

curso-escalabilidad
cerouno123!

1.- Iniciar servidor linux (micro) con nombre: Sunombre_practica
2.- Descargar putty y configurar la conexion a su server
3.- Conectarse a su servidor
4.- Instalar Dotnet:

curl -sSL -o dotnet.tar.gz https://download.microsoft.com/download/7/3/A/73A3E4DC-F019-47D1-9951-0453676E059B/dotnet-sdk-2.0.2-linux-x64.tar.gz 

sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
sudo ln -s /opt/dotnet/dotnet /usr/local/bin

5.- Probar comando dotnet (no debe mostrar error)
6.- dotnet new mvc test
7.- cd test
8.- dotnet run (no debe mostrar errores) luego Ctrl+C para terminar aplicacion
9.- instalar nginx
sudo yum install nginx
sudo service nginx start
10.- Abrir archivo nginx.conf
sudo vim /etc/nginx/nginx.conf

11.- Configurar nginx
location / {
        proxy_pass         http://localhost:5000;
        proxy_http_version 1.1;
        proxy_set_header   Upgrade $http_upgrade;
        proxy_set_header   Connection keep-alive;
        proxy_set_header   Host $http_host;
        proxy_cache_bypass $http_upgrade;
    }
12.- Guardar archivo y reiniciar nginx
sudo nginx service restart
13.- Probar sitio http://ip
