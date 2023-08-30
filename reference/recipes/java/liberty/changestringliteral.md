# Change string literal

**org.openrewrite.java.liberty.ChangeStringLiteral**

_Changes the value of a string literal._

## Source

[GitHub](https://github.com/openrewrite/rewrite-liberty/blob/main/src/main/java/org/openrewrite/java/liberty/ChangeStringLiteral.java), [Issue Tracker](https://github.com/openrewrite/rewrite-liberty/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite.recipe/rewrite-liberty/1.0.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-liberty
* version: 1.0.0

## Options

| Type | Name | Description |
| -- | -- | -- |
| `String` | valuePattern | A pattern that is used to find matching string literal. |
| `String` | newValueTemplate | The template that will replace the existing value. |


## Usage

This recipe has required configuration parameters. Recipes with required configuration parameters cannot be activated directly. To activate this recipe you must create a new recipe which fills in the required parameters. In your `rewrite.yml` create a new recipe with a unique name. For example: `com.yourorg.ChangeStringLiteralExample`.
Here's how you can define and customize such a recipe within your rewrite.yml:

{% code title="rewrite.yml" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: com.yourorg.ChangeStringLiteralExample
displayName: Change string literal example
recipeList:
  - org.openrewrite.java.liberty.ChangeStringLiteral:
      valuePattern: java:(.*)
      newValueTemplate: org:$1
```
{% endcode %}

Now that `com.yourorg.ChangeStringLiteralExample` has been defined activate it and take a dependency on org.openrewrite.recipe:rewrite-liberty:1.0.0 in your build file:
{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("6.2.4")
}

rewrite {
    activeRecipe("com.yourorg.ChangeStringLiteralExample")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-liberty:1.0.0")
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
        <version>5.4.2</version>
        <configuration>
          <activeRecipes>
            <recipe>com.yourorg.ChangeStringLiteralExample</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-liberty</artifactId>
            <version>1.0.0</version>
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

## Contributors
* [cjobinabo](mailto:chukaobinabo@gmail.com)


## See how this recipe works across multiple open-source repositories

[![Moderne Link Image](/.gitbook/assets/ModerneRecipeButton.png)](https://app.moderne.io/recipes/org.openrewrite.java.liberty.ChangeStringLiteral)

The community edition of the Moderne platform enables you to easily run recipes across thousands of open-source repositories.

Please [contact Moderne](https://moderne.io/product) for more information about safely running the recipes on your own codebase in a private SaaS.