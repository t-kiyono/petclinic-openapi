# petclinic-openapi

Petclinic アプリケーションの OpenAPI 定義ファイルおよび、そこから生成するパッケージを管理する

## パッケージのインストール

`TOKEN` には `read:packages` 以上のスコープが設定された personal access token (classic) を設定する

### Maven

pom.xml

~/.m2/settings.xml

```xml
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0 https://maven.apache.org/xsd/settings-1.0.0.xsd">
  <servers>
    <server>
      <id>github</id>
      <username>USERNAME</username>
      <password>TOKEN</password>
    </server>
  </servers>
</settings>
```

```xml
<repositories>
  <repository>
    <id>central</id>
    <url>https://repo1.maven.org/maven2</url>
  </repository>
  <repository>
    <id>github</id>
    <url>https://maven.pkg.github.com/t-kiyono/petclinic-openapi</url>
  </repository>
</repositories>

<dependencies>
  <dependency>
    <groupId>net.devfit.petclinic</groupId>
    <artifactId>openapi-spring</artifactId>
    <version>0.1.0</version>
  </dependency>
</dependencies>
```

### Gradle

build.gradle

```groovy
repositories {
  maven {
    url = uri("https://maven.pkg.github.com/t-kiyono/petclinic-openapi")
    credentials {
      username = project.findProperty("gpr.user") ?: System.getenv("USERNAME")
      password = project.findProperty("gpr.key") ?: System.getenv("TOKEN")
    }
  }
}
dependencies {
  implementation 'net.devfit.petclinic:openapi-spring:0.1.0'
}
```

### NPM

GitHub Packages への認証

```bash
$ npm login --scope=@t-kiyono --auth-type=legacy --registry=https://npm.pkg.github.com
> Username: USERNAME
> Password: TOKEN
```

依存関係の追加

```bash
$ npm install @t-kiyono/petclinic-client-ts-fetch
```
