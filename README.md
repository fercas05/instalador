
markdown
Copiar
Editar
# 🚀 Instalador 3.0 - Deploy Automatizado para Proyecto Personalizado
Este script automatiza la instalación de un entorno completo para tu proyecto, incluyendo Node.js, Git, PM2, NGINX, y más.

## 🛠️ Requisitos
- Ubuntu actualizado (20.04 o superior)
- Usuario con permisos `sudo`

## 🔧 Actualizar Ubuntu
```bash
sudo apt update
sudo apt upgrade -y
sudo apt full-upgrade -y
🧰 Instalar Git
bash
Copiar
Editar
sudo apt install git -y
👤 Crear Usuario
bash
Copiar
Editar
sudo adduser deploy
sudo usermod -aG sudo deploy
🚀 Instalación Inicial
⚠️ Usar solo en la primera instalación
Cambia el enlace y el nombre de la carpeta por los de tu proyecto:

bash
Copiar
Editar
sudo apt install -y git && \
git clone https://github.com/TU-USUARIO/TU-REPO && \
sudo chmod -R 777 TU-REPO && \
cd TU-REPO && \
sudo ./install_primaria
🔁 Instalaciones adicionales
bash
Copiar
Editar
cd TU-REPO && sudo ./instalar_instancia
⚙️ NGINX (solo si es necesario)
Editar configuración de NGINX:

bash
Copiar
Editar
sudo nano /etc/nginx/nginx.conf
Agregar antes de # server_tokens off;:

nginx
Copiar
Editar
underscores_in_headers on;
Verificar y reiniciar:

bash
Copiar
Editar
sudo nginx -t
sudo service nginx restart
📅 CRON (solo si es necesario)
Editar tareas programadas:

bash
Copiar
Editar
crontab -e
Agregar:

cron
Copiar
Editar
0 */6 * * * /usr/bin/node /usr/bin/pm2
🌐 Cambiar puerto del frontend (solo si es necesario)
Editar archivo NGINX:

bash
Copiar
Editar
sudo nano /etc/nginx/sites-enabled/instalacion-frontend
Cambiar línea:

nginx
Copiar
Editar
proxy_pass http://localhost:3004;
Editar el archivo server.js del frontend con el nuevo puerto y reiniciar servicios:

bash
Copiar
Editar
pm2 restart all
sudo service nginx restart
🔒 Licencia
Instalador script by Manuel Davila está licenciado bajo CC BY 4.0

✍️ Autor
Manuel Davila – Adaptado por TuNombre
