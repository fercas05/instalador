```bash
sudo apt update
sudo apt upgrade -y
sudo apt full-upgrade -y
```
🧰 Instalar Git
```bash
sudo apt install git -y
```
Agregue un usuario y contrasena esa contrasena no la olvide jamas

```bash
sudo adduser deploy
```
```bash
sudo usermod -aG sudo deploy
```

🔗 Instalar Node.js 18
```bash
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt install -y nodejs
node -v
npm -v
```

DESCARGAR EL INSTALADOR E INICIAR LA PRIMERA INSTALACIÓN (UTILIZAR SÓLO PARA LA PRIMERA INSTALACIÓN): cambie el link de github por el suyo y el nombre de la carpeta por el nombre del proyecto que le agregue

```bash
git clone https://github.com/fercas05/instalador
```
```bash
sudo chmod -R 777 instalador
```
```bash
cd instalador
```
```bash
sudo ./install_primaria
```

ACCEDER AL DIRECTORIO DE INSTALADOR E INICIAR INSTALACIONES ADICIONALES (USE ESTE COMANDO PARA UNA SEGUNDA O MÁS INSTALACIÓN:
```bash
cd ./instalador-3.0 && sudo ./instalar_instancia
```
Edite el archivo de configuración de nginx: (solo si es necesario)
```bash
nano /etc/nginx/nginx.conf
```

Agregue el encabezado a continuación: (justo encima de # server_tokens off;)  (solo si es necesario)
```bash
underscores_in_headers on;
```

Presiona Ctrl y X para cerrar el editor y Y para guardar los cambios.
Prueba los cambios en nginx:  (solo si es necesario)
```bash
nginx -t
```

Reinicia el servicio:  (solo si es necesario)
```bash
sudo service nginx restart
```

```bash
reinicio del servicio nginx
```

Configura CRON  (solo si es necesario)
```bash
crontab -e
0 */6 * * * /usr/bin/node /usr/bin/pm2
```

reiniciar todo  (solo si es necesario)

cambiar el puerto en etc/nginx/sites-enabled nano instalacion-frontend  (solo si es necesario)
```bash
  proxy_pass http://localhost:3004; //por el puerto nuevo
```
y cambiar el server.js del frontend por el puerto y reiniciar pm2 y nginix  (solo si es necesario)


<p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/karuapp/install2.0">Instalador script</a> by <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://manueldavila.com">Manuel Davila</a> is licensed under <a href="http://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY 4.0<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"></a></p>

