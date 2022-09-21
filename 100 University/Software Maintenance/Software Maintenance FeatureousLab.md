---
aliases: FeatureousLab
---

[[Software Maintenance Lab MOC]]

# FeatureousLab

## Setup Featureous

### Add dependencies
```xml:jhotdraw-samples/jhotdraw-samples-misc/pom.xml
<dependency>  
   <groupId>dk.sdu.mmmi</groupId>  
   <artifactId>featuretracer</artifactId>  
   <version>1.0</version>  
</dependency>  
<dependency>  
   <groupId>org.aspectj</groupId>  
   <artifactId>aspectjweaver</artifactId>  
   <version>1.9.9</version>  
</dependency>
```

```xml:jhotdraw/pom.xml
</organization>
---
<repositories>
	<repository>
		<id>GitHub</id>
		<name>GitHub external Packages</name>
		<url>https://maven.pkg.github.com/sweat-tek/MavenRepository</url>
	</repository>
</repositories>
---
<licenses>
```

### Authentication
```xml:~/.m2/settings.xml
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"  
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
 xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0  
                     http://maven.apache.org/xsd/settings-1.0.0.xsd">  
  
 <activeProfiles>  
   <activeProfile>github</activeProfile>  
 </activeProfiles>  
  
 <profiles>  
   <profile>  
     <id>github</id>  
     <repositories>  
       <repository>  
         <id>central</id>  
         <url>https://repo1.maven.org/maven2</url>  
       </repository>  
       <repository>  
         <id>github</id>  
         <url>https://maven.pkg.github.com/sweat-tek/MavenRepository</url>  
         <snapshots>  
           <enabled>true</enabled>  
         </snapshots>  
       </repository>  
     </repositories>  
   </profile>  
 </profiles>  
  
 <servers>  
   <server>  
     <id>github</id>  
     <username>pastasaucen</username>  
     <password>PAT token</password>  
   </server>  
 </servers>  
</settings>
```