# Java2js-structure-maven-plugin
Maven Plugin for generating JavaScript prototypes from Java classes and ENUMs.

## Usage
Add the GitHub repostory to your repositories in your pom.xlm file:
```
<repositories>
...
        <repository>
            <id>Maven-mvn-repo</id>
            <url>https://raw.github.com/Tusenka/Maven/mvn-repo/</url>
            <snapshots>
                <enabled>true</enabled>
                <updatePolicy>always</updatePolicy>
            </snapshots>
        </repository>
</repositories>
```
Add the plugin to your plugins in your pom.xlm file:
```
<plugins>
...
        <plugin>
             <groupId>js.generate</groupId>
             <artifactId>java2js-structure-maven-plugin</artifactId>
                        <version>1.0</version>
                        <configuration>
                        <!-- Package names from which you want to generate all classes and Enums to Javascript objects -->
                            <packagesName>
                                <param>generated</param>
                            </packagesName>
                        <!--Separate classes for which you want to generate Javascript objects. Do not include here classes from packagesName -->
                            <classesName>
                                <param>entity.Move</param>
                                <param>entity.Position</param>
                            </classesName>
                        <!--Separate enums for which you want to generate Javascript objects-->
                            <enumsName>
                                <param>entity.Side</param>
                            </enumsName>
                       </configuration>
         </plugin>
 ...
 </plugins>
```
You can use parameter  ```<jsNameSpace>``` for specify the names space for javascript classes and enums. 

You can use parameters ```<outputClassFile>``` and ```<outputEnumsFile>``` for specify the relative path to javascript files with generated JavaScript code from Java classes and Enums accordingly. 

An example of project with this plugin [here](https://github.com/Tusenka/Tavlei).
