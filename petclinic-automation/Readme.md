### web and db server automation with ansible

* please see the url for [mysql installation](https://medium.com/splunkuserdeveloperadministrator/creating-mysql-databases-with-ansible-925ab28598ab)

* first please create the `jar` file by running below command
```
   mvn package -DskipTests
```
* if required chnage the src path in copy module of jar file.
### NOTE:
* first time only script is running successfulyy , it is failing due to that mysqll flush privilages.need alter that command

