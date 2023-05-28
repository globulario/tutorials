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
