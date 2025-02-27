---
title: Koin
---

All you need to setup Koin in your project 

## Current Versions

You can find all Koin packages on [maven central](https://search.maven.org/search?q=io.insert-koin).

Here are the current available versions:

| Project   |      Version      |
|----------|:-------------:|
| koin-core |  [![Maven Central](https://img.shields.io/maven-central/v/io.insert-koin/koin-core)](https://mvnrepository.com/artifact/io.insert-koin/koin-core) |
| koin-core-coroutines |  [![Maven Central](https://img.shields.io/maven-central/v/io.insert-koin/koin-core-coroutines)](https://mvnrepository.com/artifact/io.insert-koin/koin-core-coroutines) |
| koin-test |  [![Maven Central](https://img.shields.io/maven-central/v/io.insert-koin/koin-test)](https://mvnrepository.com/artifact/io.insert-koin/koin-test) |
| koin-android |  [![Maven Central](https://img.shields.io/maven-central/v/io.insert-koin/koin-android)](https://mvnrepository.com/artifact/io.insert-koin/koin-android) |
| koin-android-test |  [![Maven Central](https://img.shields.io/maven-central/v/io.insert-koin/koin-android-test)](https://mvnrepository.com/artifact/io.insert-koin/koin-android-test) |
| koin-android-compat |  [![Maven Central](https://img.shields.io/maven-central/v/io.insert-koin/koin-android-compat)](https://mvnrepository.com/artifact/io.insert-koin/koin-android-compat) |
| koin-androidx-navigation |  [![Maven Central](https://img.shields.io/maven-central/v/io.insert-koin/koin-androidx-navigation)](https://mvnrepository.com/artifact/io.insert-koin/koin-androidx-navigation) |
| koin-androidx-workmanager |  [![Maven Central](https://img.shields.io/maven-central/v/io.insert-koin/koin-androidx-workmanager)](https://mvnrepository.com/artifact/io.insert-koin/koin-androidx-workmanager) |
| koin-compose |  [![Maven Central](https://img.shields.io/maven-central/v/io.insert-koin/koin-compose)](https://mvnrepository.com/artifact/io.insert-koin/koin-compose) |
| koin-androidx-compose |  [![Maven Central](https://img.shields.io/maven-central/v/io.insert-koin/koin-androidx-compose)](https://mvnrepository.com/artifact/io.insert-koin/koin-androidx-compose) |
| koin-androidx-compose-navigation |  [![Maven Central](https://img.shields.io/maven-central/v/io.insert-koin/koin-androidx-compose-navigation)](https://mvnrepository.com/artifact/io.insert-koin/koin-androidx-compose-navigation) |
| koin-ktor |  [![Maven Central](https://img.shields.io/maven-central/v/io.insert-koin/koin-ktor)](https://mvnrepository.com/artifact/io.insert-koin/koin-ktor) |
| koin-logger-slf4j |  [![Maven Central](https://img.shields.io/maven-central/v/io.insert-koin/koin-logger-slf4j)](https://mvnrepository.com/artifact/io.insert-koin/koin-logger-slf4j) |

## Gradle Setup

### Kotlin

Add `koin-core` dependency to your application:

```groovy
dependencies {
    
    compile "io.insert-koin:koin-core:$koin_version"
}
```

You are now ready to start Koin: 

```kotlin
fun main() {
    
    startKoin {
        modules(...)
    }
}
```

If you need testing capacity:

```groovy
dependencies {
    // Koin Test features
    testImplementation "io.insert-koin:koin-test:$koin_version"
    // Koin for JUnit 4
    testImplementation "io.insert-koin:koin-test-junit4:$koin_version"
    // Koin for JUnit 5
    testImplementation "io.insert-koin:koin-test-junit5:$koin_version"
}
```

:::info
From now you can continue on Koin Tutorials to learn about using Koin: [Kotlin App Tutorial](../quickstart/kotlin)
:::

### **Android**

Add `koin-android` dependency to your Android application:

```groovy
dependencies {

    implementation "io.insert-koin:koin-android:$koin_android_version"
}
```

You are now ready to start Koin in your `Application` class: 

```kotlin
class MainApplication : Application(){
    override fun onCreate() {
        super.onCreate()
        
        startKoin{
            modules(appModule)
        }
    }
}
```

If you need extra features, add the following needed package:

```groovy
dependencies {
    // Java Compatibility
    implementation "io.insert-koin:koin-android-compat:$koin_android_version"
    // Jetpack WorkManager
    implementation "io.insert-koin:koin-androidx-workmanager:$koin_android_version"
    // Navigation Graph
    implementation "io.insert-koin:koin-androidx-navigation:$koin_android_version"
}
```

:::info
From now you can continue on Koin Tutorials to learn about using Koin: [Android App Tutorial](../quickstart/android-viewmodel)
:::

### **Android Jetpack Compose**

```groovy
dependencies {

    implementation "io.insert-koin:koin-androidx-compose:$koin_android_compose_version"
}
```

You are now ready to start Koin in your `Application` class: 

```kotlin
class MainApplication : Application(){
    override fun onCreate() {
        super.onCreate()
        
        startKoin{
            modules(appModule)
        }
    }
}
```

:::info
From now you can continue on Koin Tutorials to learn about using Koin: [Android Compose App Tutorial](../quickstart/android-compose)
:::


### **Kotlin Multiplatform**

Add `koin-core` dependency to your multiplatform application, for shared Kotlin part:

```groovy
dependencies {
    
    compile "io.insert-koin:koin-core:$koin_version"
}
```

:::info
From now you can continue on Koin Tutorials to learn about using Koin: [Kotlin Multiplatform App Tutorial](../quickstart/kmm)
:::

### **Ktor**

Add `koin-ktor` dependency to your Ktor application:

```groovy
dependencies {
    // Koin for Ktor 
    implementation "io.insert-koin:koin-ktor:$koin_ktor"
    // SLF4J Logger
    implementation "io.insert-koin:koin-logger-slf4j:$koin_ktor"
}
```

You are now ready to install Koin feature into your Ktor application:

```kotlin
fun Application.main() {
    install(Koin) {
        slf4jLogger()
        modules(appModule)
    }
}
```

:::info
From now you can continue on Koin Tutorials to learn about using Koin: [Ktor App Tutorial](../quickstart/ktor)
:::
