+++
date = "2015-09-25T15:32:51Z"
title = "Upgrade"
[menu.main]
  identifier = "Upgrade"
  pre = "<i class='fa fa-wrench'></i>"
  weight = 50
+++

# Upgrade

Any specific upgrade information for a driver release.

## Version 3.0.0

 * Upgraded to the 3.0 version of the MongoDB Java Driver (removed deprecated methods).
 * Removed support for Scala 2.9.3 [CASBAH-182](https://jira.mongodb.org/browse/CASBAH-182)
 * Added support for Scala 2.12.0-M2 [CASBAH-179](https://jira.mongodb.org/browse/CASBAH-179)
 * MongoClientURI is now a case class for equality and hashcodes [CASBAH-151](https://jira.mongodb.org/browse/CASBAH-151)

## Version 2.8.0

Various methods have been deprecated.  This is to prepare for moving onto the
3.0 MongoDB Java driver.

## Version 2.7.0

  * In order to meet [Scala Style conventions](http://docs.scala-lang.org/style/naming-conventions.html#parentheses)
    the following 0 length argument methods have had parentheses added if there
    are side effects or removed as there are no side effects:

      * `com.mongodb.casbah.MongoClient`:
        * dbNames()
        * databaseNames()
        * getVersion
        * getConnectPoint
        * getAddress
        * getAllAddresses
        * getOptions

      * com.mongodb.casbah.MongoConnection:
        * dbNames()
        * databaseNames()
        * getVersion
        * getConnectPoint
        * getAddress
        * getAllAddresses
        * getOptions

      * com.mongodb.casbah.MongoDB:

          * collectionNames()
          * stats()
          * getName
          * getOptions

      * com.mongodb.casbah.MongoCollection:

          * getLastError()
          * lastError()

      * com.mongodb.casbah.MongoCursor:

          * count()

      * com.mongodb.casbah.map\_reduce.MapReduceResult:

          * toString()

      * com.mongodb.casbah.util.MongoOpLog:

          * next()

      * com.mongodb.casbah.gridfs.GridFSDBFile:

          * toString()

  * OpLog util fixes - Opid is now an option.
  * Scala 2.9.1 and 2.9.2 are no longer supported
  * Updated nscala-time to 0.6.0
  * `com.mongodb.casbah.MongoCollection.findOne` signatures have to
    changed to a main defaulted method
  * `com.mongodb.casbah.MongoCollection.mapReduce` may now throw an
    exception if maxDuration is exceeded
  * `com.mongodb.casbah.MongoCollection.count` and  `com.mongodb.casbah.MongoCollection.getCount` signatures have changed
    to add Duration but are defaulted.
  * `com.mongodb.casbah.WriteConcern.valueOf` now returns an Option as an
    invalid name would return a null. Any code relying on it should be
    updated.
  * `com.mongodb.casbah.commons.MongoDBList.getAs` now returns None if the
    type cast is invalid
  * `com.mongodb.casbah.commons.MongoDBObject.getAs` now returns None if
    the type cast is invalid

##  Version 2.6.1

The `com.mongodb.casbah.commons.test` dependencies are now marked in the
test classpath, so to install:

    "org.mongodb" %% "casbah-commons" % "2.6.2" % "test"

## Version 2.6.0

No upgrade needed.

## Version 2.5.1

### Scala 2.10

The -Yeta-expand-keeps-star compiler flag is no longer required.

## Version 2.5.0

### Scala 2.10

Because of how scala 2.10 handles repeated parameters you may need to
build with the -Yeta-expand-keeps-star flag to upgrade your codebase.
