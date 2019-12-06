# Original: devconf-2019-authz
Keycloak/Authorization SpringBoot example for devconf 2019

### Fine grained Authz in Keycloak
See this link for slides: https://static.sched.com/hosted_files/devconfcz2019/80/2019_Fine-Grained-Authorization-with-Keycloak-SSO.pdf

See this link for video presentation from Marek: https://www.youtube.com/watch?v=yosg4St0iUw

# How to have it running

1) Start Keycloak:
```
cd $KEYCLOAK_HOME/bin
./standalone.sh -Djboss.socket.binding.port-offset=100
```

2) Import realm cars-realm.json

3) Build
```
    mvn clean install
```    

4) Run CarsServiceApp and CarsApp from IDE (TODO: Need to describe how to run from mvn with the springboot plugin)
   Note: For the CarsServiceApp copy the images/ directory into the src/main/resource/images  so that they are on the classpath, and the change the location in the ImgUtil.java to 
   just "images/".  This will solve the "file not found" exception when trying to read the car images.

5) Go to http://localhost:8080/app and login as alice/alice or other user (See cars-realm.json for the users/passwords).

6) Switching between branches `master` for not-UMA setup (demo part1) and `authz-backup` for UMA setup (demo part2)



