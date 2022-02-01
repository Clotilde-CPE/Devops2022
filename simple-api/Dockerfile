FROM openjdk:11

# Build Main.java
RUN javac Main.java

#Run le Main.class
FROM openjdk:11-jre
COPY --from=0 /usr/src/Main.class .
CMD java Main

#Run l'appli java
FROM maven:3.6.3-jdk-11 AS myapp-build
ENV MYAPP_HOME /opt/myapp
WORKDIR $MYAPP_HOME #défini le répertoire de travail pour les instructions suivantes
COPY pom.xml . #ajoute les fichiers nécessaires
COPY src ./src
RUN mvn package -DskipTests


FROM openjdk:11-jre
ENV MYAPP_HOME /opt/myapp
WORKDIR $MYAPP_HOME
COPY --from=myapp-build $MYAPP_HOME/target/*.jar $MYAPP_HOME/myapp.jar

ENTRYPOINT java -jar myapp.jar
