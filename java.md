# Java

## Keytool

List all the certificates in Java KeyStore

```bash
keytool -v -list -keystore /Library/Java/JavaVirtualMachines/zulu-11.jdk/Contents/Home/lib/security/cacerts | grep 'Alias Name:'
```

## Multiple Java Versions 🍎

### Switch Java Versions

Switch Version

```bash
/usr/libexec/java_home -V

# Matching Java Virtual Machines (3):
#    17.0.8.1 (x86_64) "Azul Systems, Inc." - "Zulu 17.44.53" /Library/Java/JavaVirtualMachines/zulu-17.jdk/Contents/Home
#    11.0.20.1 (x86_64) "Azul Systems, Inc." - "Zulu 11.66.19" /Library/Java/JavaVirtualMachines/zulu-11.jdk/Contents/Home
#    1.8.0_372 (x86_64) "Azul Systems, Inc." - "Zulu 8.70.0.23" /Library/Java/JavaVirtualMachines/zulu-8.jdk/Contents/Home
#/Library/Java/JavaVirtualMachines/zulu-17.jdk/Contents/Home
```

then select the version from above commands result list

```bash
export JAVA_HOME=`/usr/libexec/java_home -v 11` &&
java -version
```

### jenv

To manage multiple versions `jenv` is used

`brew install jenv` installs jenv and recommends below two lines to do.  
`echo 'export PATH="$HOME/.jenv/bin:$PATH"' >> ~/.zshrc`  
`echo 'eval "$(jenv init -)"' >> ~/.zshrc`

`brew install --cask adoptopenjdk/openjdk/adoptopenjdk8` installs jdk8  
`jenv add /Library/Java/JavaVirtualMachines/adoptopenjdk-8.jdk/Contents/Home/` adds jdk8 to list of java envs  
`jenv global openjdk64-1.8.0.282` sets java version as jdk8  
`java -version` to verify  
`echo $JAVA_HOME` to verify. should point to `/Users/<username>/.jenv/versions/openjdk64-1.8.0.282`  
`jenv doctor` to verify  

`brew install --cask adoptopenjdk/openjdk/adoptopenjdk11` installs jdk11  
`jenv add /Library/Java/JavaVirtualMachines/adoptopenjdk-11.jdk/Contents/Home/` adds jdk11 to list of java envs  

`jenv enable-plugin export`  
`jenv enable-plugin maven` to enable `mvn`(maven), if being used on terminal.  

## Uninstalling Java on Mac 🍎

`sudo rm -fr /Library/Internet\ Plug-Ins/JavaAppletPlugin.plugin`  
`sudo rm -fr /Library/PreferencePanes/JavaControlPanel.prefPane`  
`sudo rm -fr ~/Library/Application\ Support/Java`  

## References

1. [Running Multiple Versions of Java on MacOS with jenv](https://mungingdata.com/java/jenv-multiple-versions-java/)
1. [How do I uninstall Java on my Mac?](https://www.java.com/en/download/help/mac_uninstall_java.html)
