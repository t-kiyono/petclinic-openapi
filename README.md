# petclinic-openapi

Petclinic アプリケーションの OpenAPI 定義ファイルおよび、そこから生成するパッケージを管理する

## パッケージのインストール

`TOKEN` には `read:packages` 以上のスコープが設定された personal access token (classic) を設定する

### Maven

pom.xml

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
```

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

### Gradle

TBD

### NPM

```bash
$ npm login --scope=@t-kiyono --registry=https://npm.pkg.github.com
> Username: USERNAME
> Password: TOKEN
> Email: PUBLIC-EMAIL-ADDRESS
```
