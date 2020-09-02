# Service Provider Interface - Creating Extensible Applications

https://docs.oracle.com/javase/tutorial/ext/basics/spi.html

### Important!

-Djava.ext.dirs is not supported anymore.

### Commands

 - Compiling:

DictionaryServiceDemo>ant compile-all

 - Creating jars:

DictionaryServiceDemo>ant jar

 - GeneralDictionary
 
\DictionaryServiceDemo\DictionaryDemo>java -cp ..\DictionaryServiceProvider\dist\*;..\GeneralDictionary\dist\*;dist\DictionaryDemo.jar dictionary.DictionaryDemo

book: a set of written or printed pages, usually bound with a protective cover
editor: a person who edits
xml: Cannot find definition for this word.
REST: Cannot find definition for this word.


 - ExtendedDictionary

\DictionaryServiceDemo\DictionaryDemo>java -cp ..\DictionaryServiceProvider\dist\*;..\ExtendedDictionary\dist\*;dist\DictionaryDemo.jar dictionary.DictionaryDemo

book: Cannot find definition for this word.
editor: Cannot find definition for this word.
xml: a document standard often used in web services, among other things
REST: an architecture style for creating, reading, updating, and deleting data that attempts to use the common vocabulary of the HTTP protocol; Representational State Transfer



### The ServiceLoader Class

From [Creating Extensible Applications](https://docs.oracle.com/javase/tutorial/ext/basics/spi.html)

> The ServiceLoader class requires that the single exposed provider type has a default constructor, which requires no arguments.

> Providers are located and instantiated on demand. A service loader maintains a cache of the providers that were loaded. Each invocation of the loader's iterator method returns an iterator that first yields all of the elements of the cache, in instantiation order. The service loader then locates and instantiates any new providers, adding each one to the cache in turn. You can clear the provider cache with the reload method.

> Extensible applications provide service points that can be extended by service providers. The easiest way to create an extensible application is to use the ServiceLoader, which is available for Java SE 6 and later. Using this class, you can add provider implementations to the application class path to make new functionality available.