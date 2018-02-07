FROM adoptopenjdk/openjdk9-openj9:jdk-9.181
RUN mkdir /opt/shareclasses
RUN mkdir /opt/app
COPY app.jar /opt/app
CMD ["java", "-Xmx128m", "-XX:+IdleTuningGcOnIdle", "-Xtune:virtualized", "-Xscmx128m", "-Xscmaxaot100m", "-Xshareclasses:cacheDir=/opt/shareclasses", "-jar", "/opt/app/app.jar"]