
# deploynexus

A simple Java library used to demonstrate building, signing, and publishing a Java artifact to **[Maven Central](https://central.sonatype.com/)** using the new Central Publishing Portal.

---

## 📦 Project Coordinates

You can include this library in your Maven or Gradle project once it’s published:

**Maven**

```xml
<dependency>
  <groupId>io.github.santacionx</groupId>
  <artifactId>deploynexus</artifactId>
  <version>1.0.0</version>
</dependency>
```

**Gradle**

```gradle
implementation 'io.github.santacionx:deploynexus:1.0.0'
```

---

## 🚀 Building and Publishing

This project is configured to:

* Package **sources** and **javadocs** JARs
* **GPG-sign** all artifacts
* Publish via the **Central Publishing Maven Plugin**

### Requirements

* Java 8+
* Maven 3.6+
* GPG installed and a valid key published to a keyserver (for signing)
* A **Sonatype Central Portal account** and **user token** stored in `~/.m2/settings.xml`

### Build Locally

```bash
mvn clean package
```

### Deploy to Maven Central

```bash
mvn -P gpg clean deploy
```

By default this will:

* Create a bundle with sources, javadocs, and signatures
* Upload it to the Central Publishing Portal
* Optionally auto-publish if `autoPublish` is enabled in the plugin config

---

## 🔑 Configuration

### `settings.xml`

Make sure your **Portal token** is stored in `~/.m2/settings.xml`:

```xml
<servers>
  <server>
    <id>central</id>
    <username>YOUR_TOKEN_USERNAME</username>
    <password>YOUR_TOKEN_PASSWORD</password>
  </server>
</servers>
```

### GPG

List keys:

```bash
gpg --list-keys
```

Export public key to a keyserver (required for Central validation):

```bash
gpg --keyserver keyserver.ubuntu.com --send-keys YOUR_KEY_ID
```

---

## 📂 Project Structure

```
deploynexus/
├── pom.xml         # Maven configuration with central-publishing
├── src/main/java   # Your main library code
└── src/test/java   # Unit tests
```

---

## 📝 License

This project is licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).

