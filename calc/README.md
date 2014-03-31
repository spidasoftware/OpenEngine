SPIDAcalc 
========

The calc repo holds all (or at least most) of the client side java code that does analysis of poles.

It is a multi component build that is pretty linearly hierarchal, with the 'calc' project at the top.

[Gradle Multi-Project](http://www.gradle.org/docs/current/userguide/multi_project_builds.html)


Building
-------

#### Requirements

* java jdk 1.7

#### Tasks

If you are in any of the individual projects running:

    gradlew build

Will make a jar and run all the tests.  Note that there are bash and batch files of the same name, so it will work on any system.

To build without any particular task like tests add the -x option

    gradle build -x test

To install a new jar in maven repo

    gradlew install

#### Notes

1.  If you are having dependency issues use the `--refresh-dependencies` flag

Testing
-------

In any of the directories with a build.gradle file running the following will test the project and all projects it depends on.

    gradlew test

If you are only interested in running the tests that are in that current project

    gradlew :test

Some to run a specific test staring in gradle 1.10

    gradlew :test --tests *SomeSpecificTest.someSpecificMethod

More examples can be found [here](http://www.gradle.org/docs/current/javadoc/org/gradle/api/tasks/testing/TestFilter.html)

#### Notes

1. There is also a [test class]() you can extend if you want a filtered stacktrace on spidasoftware.com
1. There is a testing rule that you can add for [performance testing](). It will skip that test unless you are specifically running a performance run by setting the env variable `export PERFORMANCE=true`
1. There is a circle ci rule that you can add for [ci testing](). It will skip that test when on the Circle CI servers.

Create Installer
----------------

    gradlew installer

#### Requirements
1. Have launch4j on your $PATH
    1. OS X - make sure you get the 10.8 build if you have that version.
2. Have makensis on your $PATH
    1. OS X - brew install nsis

Parts
--------

### [The Engine](engine)

<div style="float: left"><img src="images/engine.png" /></div>

This is where all the analysis happens.  It also has the model for all the structural components and engineering information.

### [The Client Editor](editor)

<div style="float: left"><img src="images/editor.png" /></div>

Where you can edit the engineering information

### [The GUI](calc)

<div style="float: left"><img src="images/gui.png" /></div>


