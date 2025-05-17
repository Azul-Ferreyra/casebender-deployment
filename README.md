Casebender Deployment

Este repositorio contiene la configuración necesaria para desplegar una instancia local de Casebender utilizando Docker y Docker Compose.

🚀 Tecnologías utilizadas

Docker

Docker Compose

Nginx

Postgres

Redis

MinIO

MISP

Cortex

Elasticsearch

✅ Requisitos previos

Tener instalado Docker y Docker Compose en tu sistema.

Tener configuradas tus claves SSH si deseas trabajar con GitHub mediante este método (recomendado).

📆 Pasos para levantar el entorno local

1. Clonar el repositorio

git clone git@github.com:Azul-Ferreyra/casebender-deployment.git
cd casebender-deployment

2. Crear tu archivo .env

Copia el archivo de ejemplo y edita tus variables de entorno:

cp .env.example .env

Edita el archivo .env con tus valores personalizados (usuarios, contraseñas, URLs, claves secretas, etc.). No uses el archivo de ejemplo directamente en producción.

3. Levantar los servicios

docker-compose up -d

Este comando iniciará todos los servicios definidos: base de datos, backend, frontend, Redis, MinIO, Cortex, Elasticsearch, y MISP.

4. Acceder a la aplicación

Casebender: http://localhost:3000

MISP: https://localhost:8443

MinIO Console: http://localhost:9090

📝 Notas

El archivo .env.example contiene valores de referencia para ayudarte a configurar tu propio .env. No contiene datos sensibles.

El archivo local-casebender.crt es un certificado autofirmado para desarrollo.

El archivo local-casebender.key (clave privada) no se encuentra en el repositorio por motivos de seguridad. Debes proveer tu propio archivo en entorno local.

Asegurate de tener configuradas correctamente tus variables de entorno para que los servicios funcionen.

❓ Ayuda

Para ver los logs de los servicios:

docker-compose logs -f

Para reiniciar los servicios:

docker-compose down
docker-compose up -d

Si necesitas regenerar tus claves SSH para GitHub:
https://docs.github.com/es/authentication/connecting-to-github-with-ssh

⚖️ Licencia

Este repositorio está bajo la licencia MIT. Consulta el archivo LICENSE para más información.

🚀 Hecho con amor y código por Azul Ferreyra.

