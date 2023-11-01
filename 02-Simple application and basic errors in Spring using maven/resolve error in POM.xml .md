## resolve error in POM.xml .

After Creating a  maven project some time we got error as follow :

![pom xml error](https://github.com/rhushikesh2000/Spring_Framework_Tutorial/assets/124034778/b32d71bd-8fb0-4cd2-aff4-2fcd89b998af)

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

![plugin](https://github.com/rhushikesh2000/Spring_Framework_Tutorial/assets/124034778/e90cf49d-ccaa-40ab-8cac-d3e386cecf33)


