# Upload files with Amazon S3 AWS SDK for Java 2.x using Spring Boot Web &middot; [![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/germanfica/tut-aws-amazon-s3-spring-boot/blob/main/LICENSE)

Upload files to your amazon s3 bucket using Spring Boot Web.

| [:sparkles: Getting Started](#getting-started) | [:rocket: Download](#download) |
| --------------- | -------- |

## Getting Started

Follow the below instructions to get started with the source code:
- [Make sure you have all Requirements](#requirements)
- [Download Source Code](#download)
- [Configure storage properties](#configure-storage-properties)
- Open Project in your favourite Java IDE and Enjoy!

## Requirements

Make sure you have the below requirements before starting:
- [OpenJDK 11 (LTS)](https://adoptium.net/?variant=openjdk11)
- [IntelliJ IDEA](https://www.jetbrains.com/idea/)
- Basic Knowledge about Spring and Java
- [AWS Account](https://aws.amazon.com/console/)
- Amazon S3 bucket

## Download
You can get access to the source code by using one of the following ways:
- :sparkles: Download Source Code
- :fire: Clone the repository locally:
```bash
git clone https://github.com/germanfica/tut-aws-amazon-s3-spring-boot.git
```

## Dependencies

- AWS Java SDK Amazon S3:

```xml
<dependencies>
  <dependency>
    <groupId>software.amazon.awssdk</groupId>
    <artifactId>s3</artifactId>
  </dependency>
</dependencies>
<dependencyManagement>
  <dependencies>
    <dependency>
      <groupId>software.amazon.awssdk</groupId>
      <artifactId>bom</artifactId>
      <version>2.17.124</version>
      <type>pom</type>
      <scope>import</scope>
    </dependency>
  </dependencies>
</dependencyManagement>
```

- Project Lombok:

```xml
<dependency>
  <groupId>org.projectlombok</groupId>
  <artifactId>lombok</artifactId>
  <version>1.18.22</version>
</dependency>
```

## Configure storage properties

Open `src/main/resources/config/storage.properties`

```
amazon.s3.bucket-name = your-bucket-name
amazon.s3.region = ${AWS_DEFAULT_REGION}
amazon.aws.credentials.access-key = ${AWS_ACCESS_KEY_ID}
amazon.aws.credentials.secret-access-key = ${AWS_SECRET_ACCESS_KEY}
```

### How to set environment variables

For more security, create environment variables in your machine, `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`, `AWS_DEFAULT_REGION` and populate it with IAM informations.

Linux or macOS

```shell
export AWS_ACCESS_KEY_ID=AKIAIOSFODNN7EXAMPLE
export AWS_SECRET_ACCESS_KEY=wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
export AWS_DEFAULT_REGION=us-west-2
```

Windows Command Prompt

```shell
setx AWS_ACCESS_KEY_ID AKIAIOSFODNN7EXAMPLE
setx AWS_SECRET_ACCESS_KEY wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
setx AWS_DEFAULT_REGION us-west-2
```

PowerShell
```shell
$Env:AWS_ACCESS_KEY_ID="AKIAIOSFODNN7EXAMPLE"
$Env:AWS_SECRET_ACCESS_KEY="wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY"
$Env:AWS_DEFAULT_REGION="us-west-2"
```

## Configure max size of upload file

Open `src/main/resources/application.properties`

```
spring.servlet.multipart.max-file-size=10MB
spring.servlet.multipart.max-request-size=10MB
```

## Run Spring Boot application
```
mvn spring-boot:run
```

## Run in Postman

If you want you can test your API using postman. I share my postman collection with you so you can fork it with the following link:

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/17519816-64bbc81f-3389-4b0b-be07-cb2f2860a10d?action=collection%2Ffork&collection-url=entityId%3D17519816-64bbc81f-3389-4b0b-be07-cb2f2860a10d%26entityType%3Dcollection%26workspaceId%3Ddcb61960-dba5-425f-b36f-d40df692531c)

## Credits
- [German Fica](https://germanfica.com/)

## External tools
None.

## License
[MIT](https://opensource.org/licenses/MIT)
