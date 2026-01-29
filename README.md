# Specsqlite
A Msgspec ORM wrapper meant to succeed the old predessor [SQLTable](https://github.com/Vizonex/SQLTable)

## Why not combine Sqlalchemy & Msgspec Together?
I'm choosing to deviate from using sqlalchmey with this project was mainly because of how hacky the process was starting to become
for sqlalchemy to accept `msgspec.Struct` types. Now when it comes to speed we can write everything in C Which should eliminate
some bottleknecks that are normally witnessed when sqlalchemy is used such as with pure-python level stuff. While 
merging them might be impossible msgspec has a different rulesets that we should follow off of and sqlalchemy 
doesn't exactly fall in line which what msgspec needs. However many things from sqlalchmey can be implemented 
hence the future use of an Appache-2.0 License with this project. I will document all the code I managed to implement 
from it's code into C. 

C has an advantage over pure python to some extent such as having faster reach to objects and being a lot more linent than 
Cython when it comes to functions such as `__new__` and also behaving as a C Extension.

This comes with [a new C-API](https://github.com/jcrist/msgspec/pull/961) that I have been implementing 
for msgspec so that it can be used in more ways such as with this library.
By giving a real example of this C-API in practice my goal is that this library 
can outperform __SQLModel__ in benchmarks and with what protocols can ultimately be serlized.

Note that development might be slow or on-and-off because I have other important libraries needing to remain maintained but hopefully
this will become a future pypi package. Y

