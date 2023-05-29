# Globular tutorials

These tutorials aim to help you learn how to create impressive and efficient web applications using Globular. The first part will cover the installation and configuration of Globular, providing an overview of its capabilities. Globular is a comprehensive web application framework that covers both the backend and the frontend. The tutorials are divided into two groups: one focuses on services and the backend, while the other focuses on applications and the frontend. By mastering the creation of services and their integration with the frontend, you can become a full-stack developer. Currently, the preferred backend language for Globular is GO, although support for C#, C++, Python, and Java is planned for the future.

For the frontend aspect of Globular, we will utilize globular-mvc, a user-friendly framework that serves as a starting point for any application. It is coded in TypeScript. Important functionalities such as login and authentication, user management, server settings, file management, and permissions management are already integrated into the framework. This allows you to concentrate on your application's main objectives instead of reinventing the wheel.

# Globular installation

Installing Globular on your computer is very simple. First of all, download the installer from [https://globular.io](https://globular.io). At the time of this writing, there are installers available for Windows and Linux. Please note that only 64-bit architectures are supported. Support for Mac OS and Raspberry Pi will be available soon.

## Linux

First of all, make sure that ffmpeg is already installed on your computer. Run the following command in the terminal:

```bash
sudo apt-get install ffmpeg
```

If you are using Linux, navigate to the directory where the package was downloaded and execute the following command:

```bash
sudo apt-get install ./globular_1.0.0-1.0.1_amd64.deb
```

Make sure to replace `globular_1.0.0-1.0.1_amd64.deb` with the actual name of the Globular package file.

For more detailed instructions, you can refer to this [article](https://medium.com/@dave.courtois60/in-this-article-i-will-guide-you-through-the-installation-and-configuration-of-your-personal-cloud-f8bdce33d33a).

If you prefer working with Docker, there is also a Docker image available. You can find detailed instructions in this [article](https://medium.com/@dave.courtois60/installing-globular-using-docker-fabd4f96b095).

## Where is Globular?

Globular functions as an application server, running as a service on your computer. To check if it is running, you can open the process manager and look for a process named 'Globular'. Since Globular is a microservice manager, you will observe multiple processes such as 'persistence_server', 'config_server', and 'sql_server'. To enable web application access to gRPC, Globular utilizes a reverse proxy called 'grpcebproxy'. Keep an eye out for this process as well. Note that each service instance requires its own reverse proxy.

## Stop Globular service

If you prefer to run Globular in the console, you can do so by stopping the service. On Linux, you can run the following command:

```bash
sudo service Globular stop
```

On Windows, you can easily stop the service named 'Globular' using the Windows Service Manager interface.

## Start Globular in the console

Now, open a command prompt. In Windows, make sure to open the prompt with administrator privileges. Navigate to the directory where Globular is installed, which is typically

 located at "C:/Program Files/Globular" in Windows or "/usr/local/share/globular" in Linux.

Once in the appropriate directory, run the following command:

```bash
sudo ./Globular
```

By running this command, you will be able to view detailed information about warnings, informational messages, and errors encountered by Globular. Additionally, you will receive messages from within the web application itself, such as JavaScript error messages.

# Globular Administration Console

Globular comes with its own administration console, which allows you to configure various server settings. The console is a comprehensive application that enables you to manage resources, access permissions, users, groups, roles, file permissions, and much more. For a detailed presentation of the console application, I recommend reading this [article](https://medium.com/@dave.courtois60/here-comes-globular-5dee34eb52f8).

To access the console application, simply navigate to the following link: [http://localhost:8080](http://localhost:8080). If needed, you can replace 'localhost' with your computer name to access the server from your local network. Further tutorials will provide more detailed information on the required functionality.

# Configuration

Network applications require a significant amount of configuration, and Globular is no exception. The configurations for Globular are stored in the file '/etc/config/config.json'. Additionally, you can read server configurations from the following HTTP address: [http://localhost:8080/config](http://localhost:8080/config).

The first thing to configure is the Name of your server. By default, your computer hostname is used as the server name. However, you can change it to a name of your choice. Keep in mind that the server name will be part of the URL, so ensure it follows the syntax and character rules for correct display.

The second property to configure is the Domain. Similar to the server name, the domain will be used in the URL. You will also need to configure the domain with your DNS provider, such as GoDaddy, for example. More information on using HTTPS will be provided later.

To access Globular from your local network, you need to configure ports. By default, Globular uses the HTTP port 8080 and the port range [10000:10100]. Each Globular service requires two ports: one for the service itself and one for its reverse-proxy. As there are currently 28 services, a minimum of 56 ports are required within the range. Ensure that these ports are available and not being used by any other application. You can change the port range as desired, but make sure there are enough ports available to run all services; otherwise, your server will behave erratically.

# Https Generate certificates

If you plan to serve content over the internet, I highly recommend configuring your server to use HTTPS instead of HTTP. To generate a certificate, follow a few simple steps. The first step is to obtain a domain name from a domain name provider such as GoDaddy, DynDNS, or any other provider. The goal is to associate your server's IP address with a specific domain. This way, people can access your server using a readable domain name instead of an IP address. It's important to note that you cannot generate a certificate for an IP address with Globular.

Once your IP is associated with the domain name, try accessing your server using the following command (replace the address with your server name and domain):

```bash
ping servername.serverdomain.com
```

You should receive a response. If not, ensure that your router is configured correctly. To do this, add port forwarding rules for port 80, port 443, and the port range 10000-10100

. Since there are many router models, I recommend referring to the documentation specific to your router for information on port forwarding.

Now, stop your server. In your configuration file, set `PortHttp` to 80 instead of 8080 and set `Protocol` to HTTPS instead of HTTP. By starting your server, you will now see in the console that the certificates have been generated. These certificates are located in the `etc/globular/config/tls` directory. Make sure this directory has the correct permission levels.

Congratulations! Your server is now accessible via HTTPS from anywhere in the world.

# What's next?

Now that Globular is up and running on your server, you have two options: creating a new microservice or creating a new web application. So you can choose between the backend and frontend tutorial.

- [Backend tutorials](backend/README.md)
- [Frontent tutorials](frontend/README.md)