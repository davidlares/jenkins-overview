
# davidJenkins

Integración demo de un proyecto "Hello World" en Java (ver 8) con Jenkins

## Instalación Jenkins

Existen distintas formas de instalar Jenkins, la mejor forma para sistemas operativos UNIX (no la más fácil), es a través de los repositorios APT

```
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt-get update
sudo apt-get install jenkins

```

## Levantando Jenkins

Una vez instado Jenkins se procede a activar el servicio dentro del servidor de desarrollo o de producción de las siguientes formas,

```
  /etc/init.d/jenkins start
  sudo systemctl start jenkins.service

```

## ngRok

Para poder registrar webhooks en GH, es necesario poder exponer el servidor de jenkins con un dominio HTTPs válido.

NgRok permite establecer este tipo de funcionalidades (ideales para entornos de desarrollo).

`./ngrok http 8080` (puerto por defecto de Jenkins)


## GitHub Webhook - Configuración Jenkins

La forma de poder comunicar Jenkins con GH, es a través de WebHooks, por lo que dentro del repositorio del proyecto se debe generar un webhook a una URL válida para lograr que esa comunicación sea factible.

![GitHub Webhook](https://i.ibb.co/L8T2pV6/webhook.png)

En las configuraciones internas de todas las tareas programadas en Jenkins es factible configurar que en procesos de CI la fuente de datos y eventos personalizados tengan origen desde las actividades generadas en Github, en commits e inclusive en ramas específicas.

![Jenkins Task 1](https://i.ibb.co/T8P4Nvx/jenkins2.png)
![Jenkins Task 2](https://i.ibb.co/vJNKFwS/jenkins.png)

## Créditos
- [David E Lares S](https://twitter.com/@davidlares3)

## Licencia

- [MIT](https://opensource.org/licenses/MIT)
