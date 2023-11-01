## resolve error in POM.xml .

After Creating a  maven project some time we got error as follow :

![pom xml error](https://github.com/rhushikesh2000/Spring_Framework_Tutorial/assets/124034778/f1b878f3-9626-4255-b941-111277cfd5d5)


To solve above error we need add belowed plug-in  inside the  build tag in POM.xml file.

Required Plugin :

~~~java
<plugins>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-war-plugin</artifactId>
        <version>3.3.2</version>
        <configuration>
          <webappDirectory>/sample/servlet/container/deploy/directory</webappDirectory>
        </configuration>
      </plugin>
    </plugins>

~~~

save and update your project.


![plugin](https://github.com/rhushikesh2000/Spring_Framework_Tutorial/assets/124034778/23304c40-7c39-4764-bd2e-78bf1fc1405c)


