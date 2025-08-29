
# 🚀 DeployNexus – Java Artifact Publishing to Maven Central

This project demonstrates an **end-to-end DevOps workflow for Java artifacts**, covering:

* ✅ Building with **Maven**
* ✅ Packaging sources & Javadocs
* ✅ **GPG-signing** artifacts
* ✅ Publishing to **Maven Central** via the **Central Publishing Portal**
* ✅ Making the library consumable in both **Maven** and **Gradle** projects

This is the same workflow followed by open-source and enterprise teams to distribute Java libraries globally.

---

## 📦 Dependency Coordinates

Once published, add it to your project:

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

## ⚙️ Key Highlights

* 📜 **Source + Javadoc JARs** packaged for distribution
* 🔑 **Signed artifacts** (industry standard for Maven Central)
* 🔄 **Reproducible builds** using Maven profiles
* 🚀 Deployment pipeline configured with **Central Publishing Plugin**
* 🛡 Secure authentication using **Sonatype Central Portal tokens**

---

## 🛠 Prerequisites

* Java **8+**
* Maven **3.6+**
* GPG installed & key published to a keyserver
* Sonatype Central Portal account with valid token in `~/.m2/settings.xml`

---

## 🚀 Workflow

### 1. Build Locally

```bash
mvn clean package
```

### 2. Deploy to Maven Central

```bash
mvn -P gpg clean deploy
```

This will:

* Bundle compiled classes, sources, and Javadocs
* Sign artifacts with GPG
* Upload securely to Maven Central

---

## 📂 Project Structure

```
deploynexus/
├── pom.xml             # Maven configuration with central-publishing plugin
├── src/main/java       # Library source code
└── src/test/java       # Unit tests
```

---

## 🔑 GPG & Publishing Setup

```bash
# List keys
gpg --list-keys  

# Export key to public keyserver (required for Central validation)
gpg --keyserver keyserver.ubuntu.com --send-keys YOUR_KEY_ID
```

---

## 📝 License

Licensed under the **Apache License 2.0**.

---

### 🌟 Why This Project Matters

This project shows practical knowledge in:

* **Java build & release engineering**
* **Artifact lifecycle management** (build → sign → publish → consume)
* **Real DevOps workflows** used in professional teams

It goes beyond just writing Java code — it demonstrates the ability to **package, secure, and distribute Java software** in the same way as widely used open-source libraries.

---



👉 Do you want me to also prepare a **parallel README for your Enterprise Task Management App** (Spring Boot + PostgreSQL + Docker) so that one shows your **backend developer strength**, while this DeployNexus shows your **DevOps strength**? That way, your GitHub will have **two showcase projects: Backend + DevOps**.
