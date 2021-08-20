# syntax=docker/dockerfile:1
FROM openjdk:8u302-jre

#Image info
LABEL org.opencontainers.image.source='https://github.com/stalerok/minecraft_forge/1.7.10/'
LABEL org.opencontainers.image.url='https://github.com/stalerok/minecraft_forge/'
LABEL org.opencontainers.image.licenses='Apache-2.0'
LABEL org.opencontainers.image.authors='https://github.com/stalerok'

WORKDIR /root/

#add forge and minecraft server
ADD https://maven.minecraftforge.net/net/minecraftforge/forge/1.7.10-10.13.4.1614-1.7.10/forge-1.7.10-10.13.4.1614-1.7.10-universal.jar /root/
ADD https://launcher.mojang.com/v1/objects/952438ac4e01b4d115c5fc38f891710c4941df29/server.jar /root/minecraft_server.1.7.10.jar

#Create folders for libraries
RUN mkdir libraries \
mkdir -p libraries/com/google/guava/guava/17.0/ \
mkdir -p libraries/com/typesafe/akka/akka-actor_2.11/2.3.3 \
mkdir -p libraries/com/typesafe/config/1.2.1 \
mkdir -p libraries/lzma/lzma/0.0.1 \
mkdir -p libraries/net/minecraft/launchwrapper/1.12 \
mkdir -p libraries/net/sf/jopt-simple/jopt-simple/4.5 \
mkdir -p libraries/org/apache/commons/commons-lang3/3.3.2 \
mkdir -p libraries/org/ow2/asm/asm-all/5.0.3 \
mkdir -p libraries/org/scala-lang/plugins/scala-continuations-library_2.11/1.0.2 \
mkdir -p libraries/org/scala-lang/plugins/scala-continuations-plugin_2.11.1/1.0.2 \
mkdir -p libraries/org/scala-lang/scala-actors-migration_2.11/1.1.0 \
mkdir -p libraries/org/scala-lang/scala-compiler/2.11.1 \
mkdir -p libraries/org/scala-lang/scala-library/2.11.1 \
mkdir -p libraries/org/scala-lang/scala-parser-combinators_2.11/1.0.1 \
mkdir -p libraries/org/scala-lang/scala-reflect/2.11.1 \
mkdir -p libraries/org/scala-lang/scala-swing_2.11/1.0.1 \
mkdir -p libraries/org/scala-lang/scala-xml_2.11/1.0.2

# Add libraries

ADD https://libraries.minecraft.net/lzma/lzma/0.0.1/lzma-0.0.1.jar libraries/lzma/lzma/0.0.1/
ADD https://libraries.minecraft.net/com/google/guava/guava/17.0/guava-17.0.jar libraries/com/google/guava/guava/17.0/
ADD https://files.minecraftforge.net/maven/com/typesafe/akka/akka-actor_2.11/2.3.3/akka-actor_2.11-2.3.3.jar libraries/com/typesafe/akka/akka-actor_2.11/2.3.3/
ADD https://files.minecraftforge.net/maven/com/typesafe/config/1.2.1/config-1.2.1.jar libraries/com/typesafe/config/1.2.1/
ADD https://libraries.minecraft.net/net/minecraft/launchwrapper/1.12/launchwrapper-1.12.jar libraries/net/minecraft/launchwrapper/1.12/
ADD https://libraries.minecraft.net/net/sf/jopt-simple/jopt-simple/4.5/jopt-simple-4.5.jar libraries/net/sf/jopt-simple/jopt-simple/4.5/
ADD https://libraries.minecraft.net/org/apache/commons/commons-lang3/3.3.2/commons-lang3-3.3.2.jar libraries/org/apache/commons/commons-lang3/3.3.2/
ADD https://libraries.minecraft.net/org/ow2/asm/asm-all/5.0.3/asm-all-5.0.3.jar libraries/org/ow2/asm/asm-all/5.0.3/
ADD https://files.minecraftforge.net/maven/org/scala-lang/plugins/scala-continuations-library_2.11/1.0.2/scala-continuations-library_2.11-1.0.2.jar libraries/org/scala-lang/plugins/scala-continuations-library_2.11/1.0.2/
ADD https://files.minecraftforge.net/maven/org/scala-lang/plugins/scala-continuations-plugin_2.11.1/1.0.2/scala-continuations-plugin_2.11.1-1.0.2.jar libraries/org/scala-lang/plugins/scala-continuations-plugin_2.11.1/1.0.2
ADD https://files.minecraftforge.net/maven/org/scala-lang/scala-actors-migration_2.11/1.1.0/scala-actors-migration_2.11-1.1.0.jar libraries/org/scala-lang/scala-actors-migration_2.11/1.1.0
ADD https://files.minecraftforge.net/maven/org/scala-lang/scala-compiler/2.11.1/scala-compiler-2.11.1.jar libraries/org/scala-lang/scala-compiler/2.11.1
ADD https://files.minecraftforge.net/maven/org/scala-lang/scala-library/2.11.1/scala-library-2.11.1.jar libraries/org/scala-lang/scala-library/2.11.1
ADD https://files.minecraftforge.net/maven/org/scala-lang/scala-parser-combinators_2.11/1.0.1/scala-parser-combinators_2.11-1.0.1.jar libraries/org/scala-lang/scala-parser-combinators_2.11/1.0.1
ADD https://files.minecraftforge.net/maven/org/scala-lang/scala-reflect/2.11.1/scala-reflect-2.11.1.jar libraries/libraries/org/scala-lang/scala-reflect/2.11.1
ADD https://files.minecraftforge.net/maven/org/scala-lang/scala-swing_2.11/1.0.1/scala-swing_2.11-1.0.1.jar libraries/org/scala-lang/scala-swing_2.11/1.0.1
ADD https://files.minecraftforge.net/maven/org/scala-lang/scala-xml_2.11/1.0.2/scala-xml_2.11-1.0.2.jar libraries/org/scala-lang/scala-xml_2.11/1.0.2

# EULA
#https://account.mojang.com/documents/minecraft_eula
RUN echo "eula=true" > eula.txt

# Ports
EXPOSE 25565

#Start command
CMD ["java", "-jar", "forge-1.7.10-10.13.4.1614-1.7.10-universal.jar"]

