Java compiler compiles java source files to `.class` files without any body. 

# Goal 
Generate empty body .class with entire outline (package, method, attributes, exceptions). 

## Usage
Java compilation does not provide full native code (like graalvm does). For the compilation process it will read only structure but not the body. So for compiliation user won't need for original jar, unless you are bundling dependencies. one can use this project to generate fake jars using which you will save lot of network bandwidth and faster compilation.


## Source
Source of this compiler is copied with only one line change to facilitate this project [link](https://github.com/eclipse/eclipse.jdt.core).

