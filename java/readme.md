# Java

## Multiple Java Versions 🍎

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
