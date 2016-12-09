# Proyecto Gradle
Proyecto gradle con la dependencia Jalopy usada anteriormente en maven

Dicha dependencia no esta especificamente para Gradle por lo que tenemos que usar las dependencias de Maven. Para usar dicha dependencia debemos de añadir esto a nuestro archivo gradle.config: 
```
repositories {
    mavenLocal()
    mavenCentral()
    maven {
        name = 'sonatype-nexus'
        url = 'https://oss.sonatype.org/content/groups/public/'
    }
}
dependencies {
    compile 'com.lukespragg:jalopy-maven-plugin:1.1.0-SNAPSHOT'
}
```
Este ultimo codigo tiene un problema y es que la dependencia com.lukespragg:jalopy-maven-plugin:1.1.0-SNAPSHOT no existe. Dicha url ha sido modificada por el desarrollador y no esta actualizada en su documentacion. La url tiene que ser sustituida por esta: 

```compile 'jalopy:jalopy:1.5b5'```

