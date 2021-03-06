# netbeans-docker
[![](https://images.microbadger.com/badges/image/openkbs/netbeans-docker.svg)](https://microbadger.com/images/openkbs/netbeans-docker "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/openkbs/netbeans-docker.svg)](https://microbadger.com/images/openkbs/netbeans-docker "Get your own version badge on microbadger.com")

* Netbeans 11 + Java 8 JDK + Maven 3.6 + Python 3.5 + Gradle 5.3 + X11 (display GUI)

# License Agreement
By using this image, you agree the [Oracle Java JDK License](http://www.oracle.com/technetwork/java/javase/terms/license/index.html).
This image contains [Oracle JDK 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html). You must accept the [Oracle Binary Code License Agreement for Java SE](http://www.oracle.com/technetwork/java/javase/terms/license/index.html) to use this image.

# Components
* java version "1.8.0_202"
  Java(TM) SE Runtime Environment (build 1.8.0_202-b08)
  Java HotSpot(TM) 64-Bit Server VM (build 25.202-b08, mixed mode)
* Apache Maven 3.6.0
* Python 3.5.2 / Python 2.7.12 + pip 19.0.3 + Python3 virtual environments
* Node v11.11.0 + npm 6.7.0 (from NodeSource official Node Distribution)
* Gradle 5.3
* Other tools: git wget unzip vim python python-setuptools python-dev python-numpy 
* X11 display desktop

# Run (recommended for easy-start)
Image is pulling from openkbs/netbeans-docker
```
./run.sh
```

# Run with docker-compose
You need to create a directory for netbeans to store configuration. 
Note, if you don't create .netbeans directory, the starting of Netbeans will fail!
(Hence, we recommend to use ./run.sh as above to start the container since the script does all the needed setup before startup.)
```
git clone https://github.com/DrSnowbird/netbeans-docker.git
cd netbeans-docker
mkdir .netbeans
docker-compose up
```

# Build
You can build your own image locally.
Note that the default build docker is "photon" version. 
If you want to build older Eclipse like "oxygen", you can following instruction in next section
```
./build.sh
```

# Configurations (Optional)
If you run "./run.sh" instead of "docker-compose up", you don't have to do anything as below.

* The container uses a default "/workspace" folder. 
* The script "./run.sh" will re-use or create the local folder in your $HOME directory with the path below to map into the docker's internal "/workspace" folder.
```
$HOME/data_docker/eclipse-phonto-docker/workspace
```
The above configuration will ensure all your projects created in the container's "/workspace" being "persistent" in your local folder, "$HOME/data_docker/eclipse-phonto-docker/workspace", for your repetitive restart docker container.

# See Also - Docker-based IDE
* [openkbs/docker-atom-editor](https://hub.docker.com/r/openkbs/docker-atom-editor/)
* [openkbs/eclipse-photon-docker](https://hub.docker.com/r/openkbs/eclipse-photon-docker/)
* [openkbs/eclipse-photon-vnc-docker](https://hub.docker.com/r/openkbs/eclipse-photon-vnc-docker/)
* [openkbs/eclipse-oxygen-docker](https://hub.docker.com/r/openkbs/eclipse-oxygen-docker/)
* [openkbs/intellj-docker](https://hub.docker.com/r/openkbs/intellij-docker/)
* [openkbs/intellj-vnc-docker](https://hub.docker.com/r/openkbs/intellij-vnc-docker/)
* [openkbs/knime-vnc-docker](https://hub.docker.com/r/openkbs/knime-vnc-docker/)
* [openkbs/netbeans9-docker](https://hub.docker.com/r/openkbs/netbeans9-docker/)
* [openkbs/netbeans](https://hub.docker.com/r/openkbs/netbeans/)
* [openkbs/papyrus-sysml-docker](https://hub.docker.com/r/openkbs/papyrus-sysml-docker/)
* [openkbs/pycharm-docker](https://hub.docker.com/r/openkbs/pycharm-docker/)
* [openkbs/scala-ide-docker](https://hub.docker.com/r/openkbs/scala-ide-docker/)
* [openkbs/sublime-docker](https://hub.docker.com/r/openkbs/sublime-docker/)
* [openkbs/webstorm-docker](https://hub.docker.com/r/openkbs/webstorm-docker/)
* [openkbs/webstorm-vnc-docker](https://hub.docker.com/r/openkbs/webstorm-vnc-docker/)

# See Also - Docker-based SQL GUI
* [Sqlectron SQL GUI at openkbs/sqlectron-docker](https://hub.docker.com/r/openkbs/sqlectron-docker/)
* [Mysql-Workbench at openkbs/mysql-workbench](https://hub.docker.com/r/openkbs/mysql-workbench/)
* [PgAdmin4 for PostgreSQL at openkbs/pgadmin-docker](https://hub.docker.com/r/openkbs/pgadmin-docker/)

# Display X11 Issue
More resource in X11 display of Eclipse on your host machine's OS, please see
* [X11 Display problem](https://askubuntu.com/questions/871092/failed-to-connect-to-mir-failed-to-connect-to-server-socket-no-such-file-or-di)
* [X11 Display with Xhost](http://www.ethicalhackx.com/fix-gtk-warning-cannot-open-display/)

# Other possible Issues
You might see the warning message or something similar in the launching xterm console like below, you can just ignore it. I googled around and some blogs just suggested to ignore since the IDE is still functional ok.
```
** (eclipse:1): WARNING **: Couldn't connect to accessibility bus: Failed to connect to socket /tmp/dbus-wrKH8o5rny: Connection refused
** (java:7): WARNING **: Couldn't connect to accessibility bus: Failed to connect to socket /tmp/dbus-wrKH8o5rny: Connection refused
```
