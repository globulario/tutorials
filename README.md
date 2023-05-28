# Globular tutorials
These tutorials aim to help you learn how to create impressive and efficient web applications using Globular. The first part will cover the installation and configuration of Globular, providing an overview of its capabilities. Globular is a comprehensive web application framework that covers both the backend and the frontend. The tutorials are divided into two groups: one focuses on services and the backend, while the other focuses on applications and the frontend. By mastering the creation of services and their integration with the frontend, you can become a full-stack developer. Currently, the preferred backend language for Globular is GO, although support for C#, C++, Python, and Java is planned for the future.

For the frontend aspect of Globular, we will utilize globular-mvc, a user-friendly framework that serves as a starting point for any application. It is coded in TypeScript. Important functionalities such as login and authentication, user management, server settings, file management, and permissions management are already integrated into the framework. This allows you to concentrate on your application's main objectives instead of reinventing the wheel.

# Globular installation
Installing Globular on your computer is very simple. First of all, download the installer from https://globular.io. At the time of this writing, there are installers available for Windows and Linux. Please note that only 64-bit architectures are supported. Support for Mac OS and Raspberry Pi will be available soon.

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
Globular functions as an application server, running as a service on your computer. To check if it is running, you can open the process manager and look for a process named 'Globular'. Since Globular is a microservice manager, you will observe multiple processes such as 'persistence_server', 'config_server', and 'sql_server'. To enable web application access to gRPC, Globular utilizes a reverse proxy called 'grpcebproxy'. Keep an eye out for this process as well. Note that each service instance require it own reverse proxy.

## Stop Globular service
If you prefer to run Globular in the console, you can do so by stopping the service. On Linux, you can run the following command:

```bash
sudo service Globular stop
```

On Windows, you can easily stop the service named 'Globular' using the Windows Service Manager interface.

## Start Globular in the console
Now, open a command prompt. In Windows, make sure to open the prompt with administrator privileges. Navigate to the directory where Globular is installed, which is typically located at "C:/Program Files/Globular" in Windows or "/usr/local/share/globular" in Linux.

Once in the appropriate directory, run the following command:

```bash
sudo ./Globular
```

By running this command, you will be able to view detailed information about warnings, informational messages, and errors encountered by Globular. Additionally, you will receive messages from within the web application itself, such as JavaScript error messages.

# Globular Administration Console
Globular comes with its own administration console, which allows you to configure various server settings. The console is a comprehensive application that enables you to manage resources, access permissions, users, groups, roles, file permissions, and much more. For a detailed presentation of the console application, I recommend reading this [article](https://medium.com/@dave.courtois60/here-comes-globular-5dee34eb52f8).

To access the console application, simply navigate to the following link: [http://localhost:8080](http://localhost:8080). If needed, you can replace 'localhost' with your computer name to access the server from your local network. Further tutorials will provide more detailed information on the required functionality.