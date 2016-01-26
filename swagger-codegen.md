Steps
====

1. mvn install 
--------------
*  wget http://ftp.riken.jp/net/apache/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz
* tar -xzvf /scratch/download/apache-maven-3.3.9-bin.tar.gz
* Add the bin directory of the created directory apache-maven-3.3.9 to the PATH environment variable

2. mvn proxy setup
------------------
    <proxies>
      <proxy>
        <id>my-proxy</id>
        <active>true</active>
        <protocol>http</protocol>
        <host>www-proxy.XXXXXXX.com</host>
        <port>80</port>
      </proxy>
    </proxies>


3. download swagger-codegen-cli-2.1.4.jar
-----------------------------------------
* wget http://repo1.maven.org/maven2/io/swagger/swagger-codegen-cli/2.1.4/swagger-codegen-cli-2.1.4.jar 
* cp swagger-codegen-cli-2.1.4.jar swagger-codegen-cli.jar

4. Use swagger-codegen-cli.jar to generate java client lib
----------------------------------------------------------

  java -jar swagger-codegen-cli.jar generate \
    -i http://x.x.x.x/nimbula.json \
    -l java \
    -o samples/client/nimbula/java


5. compile and run the client, as well as unit tests against it:
----------------------------------------------------------------

    cd samples/client/petstore/java
    mvn package


More details in https://github.com/swagger-api/swagger-codegen/blob/master/README.md#to-generate-a-sample-client-library
