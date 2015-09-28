
A start this lab to study the creation of maven plugins for a mantenance job of a old aplication generator. It uses Javadoc tags style rather than the Java 1.5 annotations style ([**ref**](https://maven.apache.org/guides/plugin/guide-java-plugin-development.html)). I'm following [Sonatype's tutorial](http://books.sonatype.com/mvnref-book/reference/writing-plugins-sect-custom-plugin.html)

# Running

For lazyness sake I didn't create a whole project to test it. I just made an alternate _pom.xml_ named _pom-test.xml_ that can be run as `mvn -f pom-test.xml greeter:greet`. Note that I by naming the plugin _greeter-maven-pluging_ according to _Maven pluging naming Convention_, I'm able to use short syntax _greeter:greet_ rather than using _groupId:archetypeId_ syntax.
By using the tag _@requiresproject_ set to false, this plugin can be run without a project. In this case, maven won't be able to use plugin prefix shorthand used previously, so it is necessary to use full _groupId:archetypeId_ syntax or to use _maven-plugin-plugin_ and _pluginGroups_ as explained in [Sonatype's tutorial](http://books.sonatype.com/mvnref-book/reference/writing-plugins-sect-custom-plugin.html).

The plugin accepts a parameter ([**ref**](http://books.sonatype.com/mvnref-book/reference/writing-plugins-sect-mojo-params.html)) named _greeter.message_ that can be passed in command line, i.e., `-Dgreeter.message='Hello World again!'`. The parameter also has a default value defined.
