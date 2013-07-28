About  
=====
This is a scons builder for Google's protocol buffers. In its current configuration, it should
be instantly deployable into a site_scons directory or similar. (ie: anywhere on scons' tool path)

Heavily based on the one located on the [Scons wiki](http://scons.org/wiki/ProtocBuilder) written by Scott Stafford.

Java support and explicit output language interface added by Steven Haywood.

Project Managementy Things  
==========================
Canonical repository: www.github.com/shaywood/scons_protoc  
Maintainer: Steven Haywood, steven.haywood.2010@my.bristol.ac.uk  

Authors:   
========
Original author: Scott Stafford  
Patches: Steven Haywood
Contributors: James Laverack

Notes:  
======
If you're targetting Java and using the "option java\_package" or "option java\_outer\_classname"
features of protoc, then try to put those option lines at the top of the file.

This is due to having to scan for them in order to correctly predict target filenames, which
will be slow for large .proto files.
