# How to Compile Gephi on Ubuntu 16.04 LTS

### 1. Get latest version of source code from github with

```sh
$ git clone git@github.com:gephi/gephi.git
```

### 2. Setup Java

By default, Ubuntu 16.04 will have OpenJDK 1.8. Gephi recommends using Oracle's JDK. To install this you must,

#### 2.1. Add Oracle's PPA, then update your package repository

```sh
$ sudo add-apt-repository ppa:webupd8team/java
$ sudo apt-get update
```

#### 2.2 Get the latest version of Java from Oracle

```sh
$ sudo apt-get install oracle-java8-installer
```

#### 2.3 Make sure you are using the Oracle version of Java and find its path using

```sh
$ sudo update-alternatives --config java
```

The path will most likely be /usr/lib/jvm/java-8-oracle/jre/bin/java

For more information on managing multiple version of Java on Ubuntu take a look at https://www.digitalocean.com/community/tutorials/how-to-install-java-with-apt-get-on-ubuntu-16-04

### 3. Setup Netbeans

#### 3.1 Download the latest version of Neatbeans

The Java EE version is enough to compile Gephi. Make sure you pick linux as your os.

#### 3.2 Run the installation script

```sh
$ cd Downloads
$ chmod +x <downloaded file name>.sh
$./<downloaded file name>.sh
```

Follow the instructions until you are asked to locate JDK. The default path is /usr. Set the path to /usr/lib/jvm. Finish install netbeans.

### 4. Compile Gephi

Go back to the directory where you git cloned gephi and run
```sh
$ mvn clean install
```
Compiling takes 10/20 minutes on a Dual core Xeon HP Z600 workstation with SSD, so expect to wait a bit..

Voilà, you are done.
