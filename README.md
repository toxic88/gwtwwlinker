gwtwwlinker
===========

HTML5 web worker for GWT with Elemental

About
----

This sample code shows how to compile GWT module to be used as HTML5 web worker.

`WorkerLinker` is the linker responsible for generating javascript code with minimal GWT overhead (like $wnd and $doc dependencies). Javascript template, located in series of print() commands, contains declaration of `$workergwtbridge` variable. It also registers message handler, which will pass data received from main process and pass it to `$workergwtbridge`.

`SampleWorker` is a class intended to run as worker, compiled with `WorkerLinker`. In `onModuleLoad` it instatiates `$workergwtbridge` function, which is now able to perform calculations implemented in GWT/Java and send back results.

`WebApp` is a simple GWT app which controls `SampleWorker` with Worker class from [GWT Elemental] package and shows data sent back from worker.

Remarks
----
* Sample gwt.xml's contains only Firefox permutation (`gecko1_8`), demo is compiled with this setting as well
* There is no automated permutation compilation/naming, you have to work it out yourself (feel free to send patch afterward)
* There is no automated permutation selection either
* Sorry for plain Eclipse project, I'm not yet Maven-educated


Author
----
Tomasz Zieliński, tomasz.zielinski@gmail.com

License
----
Licensed under the Apache License, Version 2.0

Attribution
----
WorkerLinker class is directly derived from Titaniumj Mobile linker licensed under the Apache License, Version 2.0:
https://github.com/emitrom/titanium4j/blob/master/src/com/emitrom/ti4j/mobile/linker/TiMobileLinker.java

[GWT Elemental]: http://www.instantshift.com/2013/11/19/html5-features-with-gwt-elemental/