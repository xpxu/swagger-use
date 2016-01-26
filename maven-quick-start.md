1. 使用maven创建一个helloworld
------------------------------
mvn archetype:generate -DgroupId=maven.demo.start -DartifactId=HelloMaven -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false

2.工程目录结构
--------------
    HelloMaven  
    |-- pom.xml  
    `-- src  
        |-- main  
        |   `-- java  
        |       `-- maven  
        |           `-- demo  
        |               `-- start  
        |                   `-- App.java  
        `-- test  
            `-- java  
                `-- maven  
                    `-- demo  
                        `-- start  
                            `-- AppTest.java  

3. 工程编译打包，并测试。
-----------------------
切换到刚才创建的项目的目录中，执行mvn package命令：

4. 手动执行maven.demo.start.App
-------------------------------
java -cp target/HelloMaven-1.0-SNAPSHOT.jar maven.demo.start.App
