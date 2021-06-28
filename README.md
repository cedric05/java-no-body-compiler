## update
Latest update includes eclipse 4.20 release ecj
> - base [url](https://download.eclipse.org/eclipse/downloads/drops4/R-4.20-202106111600)
> - download [url](https://download.eclipse.org/eclipse/downloads/drops4/R-4.20-202106111600/download.php?dropFile=ecjsrc-4.20.jar)


Java compiler compiles java source files to `.class` files without any body. 

# Goal 
Generate empty body .class with entire outline (package, method, attributes, exceptions). 

## Usage
Java compilation does not provide full native code (like graalvm does). For the compilation process it will read only structure but not the body. So for compiliation user won't need for original jar, unless you are bundling dependencies. one can use this project to generate fake jars using which you will save lot of network bandwidth and faster compilation.

download [javac-no-body.jar](https://github.com/cedric05/java-no-body-compiler/releases/download/v4.20/java-no-body-compiler-refs.tags.v4.20.jar)

```bash
java -jar javac-no-body.jar file.java
```

## example 
compile jdk source and generated [rt+javax+sun...jar](https://github.com/cedric05/java-no-body-compiler/releases/download/4.17-snapshot/rt-stub.jar.zip) size: 4.81MB. Original rt.jar size: 60+ MB 


## Source
Source of this compiler is copied with only one line change to facilitate this project [link](https://github.com/eclipse/eclipse.jdt.core).

jdt-core source is scrambled across multiple folders for above github repo. For easy access use [this link](#update)

```diff
---- a/org/eclipse/jdt/internal/compiler/ast/CompilationUnitDeclaration.java
++++ b/org/eclipse/jdt/internal/compiler/ast/CompilationUnitDeclaration.java
<       public boolean ignoreMethodBodies = false;
---
>       public boolean ignoreMethodBodies = true;

```


beware and bewarned,This project will not be helpful in real world senario.

Its for Pure research and educational purpose. 
