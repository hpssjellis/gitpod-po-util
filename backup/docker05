FROM gitpod/workspace-full:latest

USER root

RUN apt-get update                                                                                               \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends dbus gcc g++ automake           \
               libtool lsb-release make  clang-format-6.0   libdbus-1-dev libboost-dev libreadline-dev           \                                     
               autoconf autoconf-archive  software-properties-common bsdtar                                      \
               sudo curl git gzip python gnupg2 software-properties-common build-essential libarchive-zip-perl   \
               gcc-multilib                                                                                      \
    && apt-get update                                                                                            \
    && /bin/bash -c "bash <(curl -sL https://particle.io/install-cli)"                                           \
    && /bin/bash -c "bash <(curl -sL get.po-util.com)"                                                           \
    && po                                                                                                        \
    && chown -R gitpod:gitpod /home/gitpod/.po-util                                                              \
    && chmod -R 777 /home/gitpod/.po-util                                                                        
 
 
 
 
 #RUN  dpkg --add-architecture i386  \
#      && apt-get update         \
 #     && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends lib32z1 lib32ncurses5 lib32bz2-1.0 lib32stdc++6
    
    
    
 #  && apt-get update                \
 # && dpkg --add-architecture i386    \
 #&& apt-get update                  \ 
 # && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends libncurses5:i386 libreadline libglib2.0-dev 
    
# try                lib32z1 lib32ncurses5 lib32bz2-1.0 lib32stdc++6
## NOTE: not installing libreadline and libglib2.0-dev  libncurses5:i386  may cause some issues

# will clean folders last   
    
    
# Get gcc-arm-embedded key
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys B4D03348F75E3362B1E1C2A1D1FAA6ECF64D33B0

# Add ggc-arm-embedded ppa
RUN echo "deb http://ppa.launchpad.net/team-gcc-arm-embedded/ppa/ubuntu bionic main" > /etc/apt/sources.list.d/team-gcc-arm-embedded-ubuntu-ppa-bionic.list

# Install gcc-arm-armbedded
RUN apt update && apt install -y --no-install-recommends \
    gcc-arm-embedded \
 && rm -rf /var/lib/apt/lists/*  
    
    
#RUN  sudo apt-get install  lib32z1  lib32bz2-1.0 lib32stdc++6   
    
    
    
 

USER gitpod
  
RUN mkdir -p /home/gitpod/logs                                                                            \ 
    && touch /home/gitpod/logs/myDockerlog.txt                                                            \
    && echo "Installation start, made some folders in /home/gitpod" >> /home/gitpod/logs/myDockerlog.txt  \
    && echo "Installation end"                                      >> /home/gitpod/logs/myDockerlog.txt  
   

# Give back control
USER root


# Cleaning
RUN apt-get clean  && rm -rf /var/cache/apt/* && rm -rf /var/lib/apt/lists/* && rm -rf /tmp/*
