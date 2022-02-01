FROM openjdk:11
# Build Main.java
# TODO : in next steps (not now)

FROM openjdk:11-jre
# Copy resource from previous stage
??COPY Main.class clotilde.long/Devops2022/Basics
COPY --from=0 /usr/src/Main.class .

# Run java code with the JRE
??CMD java Main
# TODO : in next steps (not now)
