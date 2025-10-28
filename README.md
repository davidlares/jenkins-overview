
## Jenkins overview

Demo integration of a "Hello World" project in Java (version 8) with Jenkins

## Installing Jenkins

There are several ways to install Jenkins. The best way for UNIX operating systems (not the easiest) is through APT repositories.

```
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt-get update
sudo apt-get install jenkins
```

## Starting Jenkins

Once Jenkins is installed, activate the service on the development or production server in the following ways.

```
/etc/init.d/jenkins start
sudo systemctl start jenkins.service
```

## ngRok

To register webhooks in GH, you must be able to expose the Jenkins server with a valid HTTPS domain. NgRok allows you to configure this type of functionality (ideal for development environments).

`./ngrok http 8080`

(Jenkins default port)

## GitHub Webhooks - Jenkins Configuration

Jenkins communicates with GH through Webhooks. Therefore, a webhook must be generated within the project repository to a valid URL to make this communication possible.

https://i.ibb.co/L8T2pV6/webhook.png

In the internal configurations of all scheduled tasks in Jenkins, it's possible to configure CI processes to source custom data and events from activities generated on GitHub, commits, and even specific branches.

https://i.ibb.co/T8P4Nvx/jenkins2.png
https://i.ibb.co/vJNKFwS/jenkins.png

## Credits
[David Lares S](https://davidlares.com)

## License
[MIT](https://opensource.org/licenses/MIT)
