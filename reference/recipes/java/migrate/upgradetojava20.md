# Migrate to Java 20

**org.openrewrite.java.migrate.UpgradeToJava20**

_This recipe will apply changes commonly needed when migrating to Java 20. This recipe will also replace deprecated API with equivalents when there is a clear migration strategy. Build files will also be updated to use Java 20 as the target/source and plugins will be also be upgraded to versions that are compatible with Java 20._

### Tags

* java20

## Source

[GitHub](https://github.com/openrewrite/rewrite-migrate-java/blob/main/src/main/resources/META-INF/rewrite/java-version-20.yml), [Issue Tracker](https://github.com/openrewrite/rewrite-migrate-java/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite.recipe/rewrite-migrate-java/2.0.7/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-migrate-java
* version: 2.0.7


## Usage

This recipe has no required configuration options. It can be activated by adding a dependency on `org.openrewrite.recipe:rewrite-migrate-java:2.0.7` in your build file or by running a shell command (in which case no build changes are needed): 
{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("6.1.18")
}

rewrite {
    activeRecipe("org.openrewrite.java.migrate.UpgradeToJava20")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-migrate-java:2.0.7")
}
```
{% endcode %}
{% endtab %}
{% tab title="Maven POM" %}
{% code title="pom.xml" %}
```markup
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>5.3.2</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.java.migrate.UpgradeToJava20</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-migrate-java</artifactId>
            <version>2.0.7</version>
          </dependency>
        </dependencies>
      </plugin>
    </plugins>
  </build>
</project>
```
{% endcode %}
{% endtab %}

{% tab title="Maven Command Line" %}
{% code title="shell" %}
You will need to have [Maven](https://maven.apache.org/download.cgi) installed on your machine before you can run the following command.

```shell
mvn -U org.openrewrite.maven:rewrite-maven-plugin:run \
  -Drewrite.recipeArtifactCoordinates=org.openrewrite.recipe:rewrite-migrate-java:RELEASE \
  -Drewrite.activeRecipes=org.openrewrite.java.migrate.UpgradeToJava20
```
{% endcode %}
{% endtab %}
{% endtabs %}

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Migrate to Java 17](../../java/migrate/upgradetojava17.md)
* [Change Maven Java version property values to 20](../../java/migrate/javaversion20.md)
* [Prefer `Locale.of(..)` over `new Locale(..)`](../../java/migrate/util/uselocaleof.md)
* [Replace deprecated Runtime.Exec() methods](../../staticanalysis/replacedeprecatedruntimeexecmethods.md)

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.migrate.UpgradeToJava20
displayName: Migrate to Java 20
description: This recipe will apply changes commonly needed when migrating to Java 20. This recipe will also replace deprecated API with equivalents when there is a clear migration strategy. Build files will also be updated to use Java 20 as the target/source and plugins will be also be upgraded to versions that are compatible with Java 20.

tags:
  - java20
recipeList:
  - org.openrewrite.java.migrate.UpgradeToJava17
  - org.openrewrite.java.migrate.JavaVersion20
  - org.openrewrite.java.migrate.util.UseLocaleOf
  - org.openrewrite.staticanalysis.ReplaceDeprecatedRuntimeExecMethods

```
{% endtab %}
{% endtabs %}

## Contributors
* [Sam Snyder](mailto:sam@moderne.io)
* [Shannon Pamperl](mailto:shanman190@gmail.com)
* [Nick McKinney](mailto:mckinneynicholas@gmail.com)
* Tyler Van Gorder
* [Tim te Beek](mailto:tim.te.beek@jdriven.com)
* [Knut Wannheden](mailto:knut@moderne.io)
* [traceyyoshima](mailto:tracey.yoshima@gmail.com)
* [Jonathan Schneider](mailto:jkschneider@gmail.com)
* Kun Li
* Aaron Gershman
* [Patrick](mailto:patway99@gmail.com)
* [Aaron Gershman](mailto:aegershman@gmail.com)
* [Jonathan Schnéider](mailto:jkschneider@gmail.com)
* [Kun Li](mailto:kun@moderne.io)
* Aakarshit Uppal
* [Tim te Beek](mailto:tim@moderne.io)
* Josh Soref


## See how this recipe works across multiple open-source repositories

[![Moderne Link Image](/.gitbook/assets/ModerneRecipeButton.png)](https://app.moderne.io/recipes/org.openrewrite.java.migrate.UpgradeToJava20)

The community edition of the Moderne platform enables you to easily run recipes across thousands of open-source repositories.

Please [contact Moderne](https://moderne.io/product) for more information about safely running the recipes on your own codebase in a private SaaS.
