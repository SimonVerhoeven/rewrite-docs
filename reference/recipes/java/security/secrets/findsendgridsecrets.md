# Find SendGrid secrets

**org.openrewrite.java.security.secrets.FindSendGridSecrets**
_Locates SendGrid secrets stored in plain text in code._

### Tags

* security

## Source

[Github](https://github.com/openrewrite/rewrite-java-security), [Issue Tracker](https://github.com/openrewrite/rewrite-java-security/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite.recipe/rewrite-java-security/1.19.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-java-security
* version: 1.19.0


## Usage

This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite.recipe:rewrite-java-security:1.19.0 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.32.0")
}

rewrite {
    activeRecipe("org.openrewrite.java.security.secrets.FindSendGridSecrets")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-java-security:1.19.0")
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
        <version>4.37.0</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.java.security.secrets.FindSendGridSecrets</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-java-security</artifactId>
            <version>1.19.0</version>
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
```shell
mvn org.openrewrite.maven:rewrite-maven-plugin:4.37.0:run \
  -Drewrite.recipeArtifactCoordinates=org.openrewrite.recipe:rewrite-java-security:1.19.0 \
  -DactiveRecipes=org.openrewrite.java.security.secrets.FindSendGridSecrets
```
{% endcode %}
{% endtab %}
{% endtabs %}

Recipes can also be activated directly from the command line by adding the argument `-Drewrite.activeRecipes=org.openrewrite.java.security.secrets.FindSendGridSecrets`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Find secrets with regular expressions](../../../java/security/secrets/findsecretsbypattern.md)
  * secretName: `SendGrid API key`
  * valuePattern: `SG\.[a-zA-Z0-9_-]{22}\.[a-zA-Z0-9_-]{43}`

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.security.secrets.FindSendGridSecrets
displayName: Find SendGrid secrets
description: Locates SendGrid secrets stored in plain text in code.
tags:
  - security
recipeList:
  - org.openrewrite.java.security.secrets.FindSecretsByPattern:
      secretName: SendGrid API key
      valuePattern: SG\.[a-zA-Z0-9_-]{22}\.[a-zA-Z0-9_-]{43}

```
{% endtab %}
{% endtabs %}