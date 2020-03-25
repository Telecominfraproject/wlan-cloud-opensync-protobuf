# tip-wlan-opensync-protobuf

The scripts in this repository produce maven artifact that has all the java classes generated from the opensync protobuf definitions.
The protobuf files are taken from [Opensync repo](https://github.com/plume-design/opensync/tree/master/interfaces)

Build instructions
* make sure java jdk 9+ is installed
* make sure maven is installed
* make sure protoc version 2.6.1 is installed
* configure maven settings.xml with repository credentials
* vim ~/.m2/settings.xml
```
<settings>
  <servers>
    <server>
      <id>io.cloudrepo</id>
      <username>repo_user</username>
      <password>password</password>
    </server>
  </servers>
</settings>
```
* configure maven toolchains.xml file with the location of the protoc executable
* $ vim ~/.m2/toolchains.xml
```
<?xml version="1.0" encoding="utf-8"?>
<toolchains>
    <!-- protocol buffer 2.6.1 -->
    <toolchain>
        <type>protobuf</type>
        <provides>
            <version>2.6.1</version>
            <vendor>google</vendor>
        </provides>
        <configuration>
            <protocExecutable>/opt/local/bin/protoc</protocExecutable>
        </configuration>
    </toolchain>
</toolchains>
```
* $ mvn clean install

Results are in tip-wlan-opensync-protobuf/target/tip-wlan-opensync-protobuf-0.0.1-SNAPSHOT.jar
