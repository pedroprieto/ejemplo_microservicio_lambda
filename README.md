# Ejemplo de despliegue automático de una aplicación SPA en S3

## Instalación de dependencias

```sh
npm install
```

## Creación de la aplicación
En primer lugar es necesario actualizar el rol en el archivo `package.json` indicando el ARN de `LabRole` del laboratorio de AWS.

```sh
npm run deployApp 
```

El script creará los siguientes recursos:
- Tabla DynamoDB
- Función Lambda

Además, se creará el archivo `claudia.json` que será necesario **almacenarlo en el repositorio**, ya que almacena referencia a los recursos creados.

## Despliegue continuo en GitHub Actions
Se proporciona el archivo `workflow.yml.example` con una plantilla de ejemplo para crear un fichero `.github/workflows/despliegue.yml`. Es necesario configurar los secretos de repositorio para almacenar las credenciales de AWS:
- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `AWS_SESSION_TOKEN`


## Borrado de recursos

```sh
npm run destroyApp
```
