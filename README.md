#This guide covers setting up a basic Gradle project using the Command Line Interface (CLI). Gradle is a powerful build automation tool used for Java, Kotlin, and other programming languages.

Prerequisites
Java Development Kit (JDK) installed (version 8 or later).

Gradle installed or use the Gradle Wrapper (recommended).
# Setup of basic gradle using cli:
```agsl
gradle init --use-defaults --type java-application
```

The above command will setup a basic gradle project

```agsl
./gradlew build
```

To prepare a jar which is executable, you need to setup manifest property in `build.gradle` to identify what is the main class to execute
```groovy
jar {
    manifest {
        attributes (
            'Main-Class': 'org.example.Main'
        )
    }
}

```


The above command can build your project

```agsl
./gradlew jar
```

The above command creates a new jar file in `build/libs` folder

```agsl
java -jar build/libs/filename.jar

```
```agsl
MyGradleProject/
├── build.gradle           # Gradle build configuration
├── settings.gradle        # Gradle settings
├── gradlew                # Gradle Wrapper script (UNIX)
├── gradlew.bat            # Gradle Wrapper script (Windows)
├── gradle/                # Wrapper support files
├── src/
    ├── main/
        ├── java/          # Application code
            └── App.java   # Sample main class (if you chose 'application')
    ├── test/
        ├── java/          # Test code
            └── AppTest.java # Sample test class
````

````agsl
plugins {
    id 'java'
    id 'application'
}

application {
    mainClass = 'com.example.App' // Replace with your main class
}

repositories {
    mavenCentral()
}

dependencies {
    implementation 'org.apache.commons:commons-lang3:3.12.0'
    testImplementation 'junit:junit:4.13.2'
}
````

The above command will execute the code


Try to build a jar and run it directly from cli and see if the okhttp code is working or not just like it is working by running directly from intellij
instead of okhttp try to integrate retrofit library to make the same http call

Prerequisites
Java Development Kit (JDK) installed.

Gradle installed or use the Gradle Wrapper (recommended).



