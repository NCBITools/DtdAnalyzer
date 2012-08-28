﻿<h1>DtdAnalyzer</h1>

<h2>Overview</h2>

This tool will create an XML representation (using elements and attributes)
of an XML DTD.

<h2>Usage</h2>

    java -jar dtdanalyzer.jar [xml] [xsl] [output] {optional: catalog}

    java gov.ncbi.pmc.dtdanalyzer.Application  [xml] [xsl] [output] {optional: catalog}

Where:
   xml     = xml instance filename
   xsl     = xsl instance
   output  = file to which output will be written
   catalog = OASIS catalog for entity resolution

This generates an XML representation of the DTD specified in the DOCTYPE declaration
in the XML instance file.

<h2>XML Structure</h2>

    elements
        element+
            @name @dtdOrder @model @note @modelNote @group
        attributes?
            attribute+
                @attName @mode @type [content is the attribute value]
        context
            parent*

<h2>Development environment</h2>

The development environment for this project is very rudimentary at present,
and uses make.  Here are the contents:

  - Makefile - targets are:

        * all - default target, everything below.
        * clean - deletes intermediate files
        * build - compiles all .java → .class; results go into 'class' directory
        * doc - builds javadocs; puts results into 'doc'
        * t - runs the script over the test file in the 'test' directory

  - setenv.sh - sets up PATH and CLASSPATH to point to the (hard-coded) development
    directories

  - bin - directory containing the script contextmodel.sh

  - src/pmctools/*.java - the Java source files

  - test/*.xml - a few samples files

<h2>Dependencies</h2>

The following jar files are required.  If you execute this as a jar file (with the "-jar"
option) then these need to be in the same directory as the datadictionaryapplication.jar.
  - resolver.jar
  - saxon.jar
  - xercesImpl.jar
  - xml-apis.jar

This utility is dependent on the <a href='http://xerces.apache.org/xerces2-j/'>Apache
Xerces2 Java parser</a>, version 2.4.0 or later.

<h2>Discussion forum / mailing list</h2>

Please join the <a href='https://groups.google.com/d/forum/dtdanalyzer'>DtdAnalyzer Google group</a>
for discussions.

<h2>Public domain</h2>

This work is in the public domain and may be used and reproduced without special permission.
