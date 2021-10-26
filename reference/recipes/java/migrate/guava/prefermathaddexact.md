# Prefer `Math#addExact`

** org.openrewrite.java.migrate.guava.PreferMathAddExact**
_This method exists in the Java standard library now._

### Tags

* guava

## Source

[Github](https://github.com/openrewrite/rewrite-migrate-java), [Issue Tracker](https://github.com/openrewrite/rewrite-migrate-java/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite.recipe/rewrite-migrate-java/0.11.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-migrate-java
* version: 0.11.0


## Usage

This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite.recipe:rewrite-migrate-java:0.11.0 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.14.0")
}

rewrite {
    activeRecipe("org.openrewrite.java.migrate.guava.PreferMathAddExact")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-migrate-java:0.11.0")
}
```
{% endcode %}
{% endtab %}

{% tab title="Maven" %}
{% code title="pom.xml" %}
```markup
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>4.15.0</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.java.migrate.guava.PreferMathAddExact</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-migrate-java</artifactId>
            <version>0.11.0</version>
          </dependency>
        </dependencies>
      </plugin>
    </plugins>
  </build>
</project>
```
{% endcode %}
{% endtab %}
{% endtabs %}

Recipes can also be activated directly from the command line by adding the argument `-DactiveRecipe=org.openrewrite.java.migrate.guava.PreferMathAddExact`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Change method name](../../../java/changemethodname.md)
  * methodPattern: `com.google.common.math.IntMath checkedAdd(..)`
  * newMethodName: `addExact`
* [Change method target to static](../../../java/changemethodtargettostatic.md)
  * methodPattern: `com.google.common.math.IntMath addExact(..)`
  * fullyQualifiedTargetTypeName: `java.lang.Math`

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.migrate.guava.PreferMathAddExact
displayName: Prefer `Math#addExact`
description: This method exists in the Java standard library now.
tags:
  - guava
recipeList:
  - org.openrewrite.java.ChangeMethodName:
      methodPattern: com.google.common.math.IntMath checkedAdd(..)
      newMethodName: addExact
  - org.openrewrite.java.ChangeMethodTargetToStatic:
      methodPattern: com.google.common.math.IntMath addExact(..)
      fullyQualifiedTargetTypeName: java.lang.Math

```
{% endtab %}
{% endtabs %}