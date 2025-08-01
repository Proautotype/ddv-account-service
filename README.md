# Application-Authentication-Service

This project uses **Quarkus**, the Supersonic Subatomic Java Framework.

For more information about Quarkus, please visit its official website: [Quarkus.io](https://quarkus.io/).

## Running the Application in Dev Mode

You can run your application in **dev mode**, which enables live coding, using the following command:

```bash
./mvnw quarkus:dev
```

> **_Note:_** Quarkus includes a **Dev UI** that's available in dev mode at: [http://localhost:8080/q/dev/](http://localhost:8080/q/dev/).

## Packaging and Running the Application

The application can be packaged using the following command:

```bash
./mvnw package
```

This will generate the `quarkus-run.jar` file in the `target/quarkus-app/` directory. Note that this is not an **über-jar**, as the dependencies are copied into the `target/quarkus-app/lib/` directory.

You can run the application using:

```bash
java -jar target/quarkus-app/quarkus-run.jar
```

### Creating an Über-Jar

If you'd like to build an **über-jar**, use the following command:

```bash
./mvnw package -Dquarkus.package.jar.type=uber-jar
```

The application packaged as an **über-jar** can then be run using:

```bash
java -jar target/*-runner.jar
```

## Creating a Native Executable

You can create a native executable using the following command:

```bash
./mvnw package -Dnative
```

If you don't have GraalVM installed, you can run the native executable build in a container using:

```bash
./mvnw package -Dnative -Dquarkus.native.container-build=true
```

Once the build is complete, you can execute the native executable with:

```bash
./target/quarkus-base-template-v2-1.0.0-SNAPSHOT-runner
```

For more information on building native executables, refer to the [Quarkus Maven Tooling Guide](https://quarkus.io/guides/maven-tooling).

## Related Guides

- **REST Jackson**: [Guide](https://quarkus.io/guides/rest#json-serialisation) - Jackson serialization support for Quarkus REST. This extension is not compatible with the `quarkus-resteasy` extension, or any of its dependent extensions.

- **Kotlin**: [Guide](https://quarkus.io/guides/kotlin) - Learn how to write your services in Kotlin with Quarkus.

## Provided Code

### REST

This template easily starts your REST Web Services.

[See Related Guide Section...](https://quarkus.io/guides/getting-started-reactive#reactive-jax-rs-resources)

## Configuration

### Log Configuration
```properties
quarkus.log.level=INFO
quarkus.log.category."org.hibernate".level=INFO
```

### Test DB Configurations
```properties
########## Test DB Configs ##########
test.quarkus.datasource.db-kind=h2
test.quarkus.datasource.jdbc.url=jdbc:h2:mem:default
test.quarkus.datasource.username=user
test.quarkus.datasource.password=password
test.quarkus.hibernate-orm.database.generation=drop-and-create
```

### DB Configurations
```properties
###### DB Configs ######
quarkus.datasource.db-kind=mariadb
quarkus.datasource.jdbc.url=jdbc:mariadb://localhost:3306/quarkus_base_template_db?useSsl=false&allowPublicKeyRetrieval=true
quarkus.datasource.username=root
quarkus.datasource.password=password
quarkus.hibernate-orm.database.generation=drop-and-create
quarkus.hibernate-orm.dialect=org.hibernate.dialect.MariaDBDialect
```

### Microprofile REST Client Configuration
```properties
########## Microprofile REST Client Configuration (https://quarkus.io/guides/rest-client-reactive) ##########
quarkus.rest-client.alpn=true
quarkus.rest-client.follow-redirects=true
quarkus.rest-client.logging.scope=request-response
quarkus.rest-client.logging.body-limit=3000
quarkus.log.category."org.jboss.resteasy.reactive.client.logging".level=DEBUG

quarkus.rest-client.shelve-service.url=http://localhost:8081
quarkus.rest-client.shelve-service.scope=jakarta.inject.Singleton
```# ddv-account-service
