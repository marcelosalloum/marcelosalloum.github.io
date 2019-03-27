---
layout: post
title: 'iOS Persistence - [1] CoreData'
published: true
---

_This is the first of a series 5-post series, each one focusing on one different way to persist data in your iOS application. Each post will contain a reference to a recommended library or a piece of code, so you can start using it in your own application._

Since I first started developing apps, I realized the importance of having a way to persist your data, so it remaisns available for the user accross the following launches.

There are a range of different ways to do that and today we are going to focus on the ones that are available in iOS out-of-the-box, which are:
- **CoreData**: a not-exactly-database, that does most of what would be expected from an actual database. You can have a look omn the official docs [here](https://developer.apple.com/documentation/coredata).
- **User Defaults**: user’s defaults database, where you store key-value pairs persistently across launches of your app.
- **Keychain**: similar to user Defaults, but is encrypted and can be shared through different devices
- **File system**: basically storing files for further usage, which includes cached images, music, videos, and more specific kinds of data.
- **SQLite**: often used through external libraries like Realm and FMDB, it is the official built-in database supported by Apple.

---
**CoreData**
Core Data is Apple’s first solution for persistence, it allows applications to persist data of any form and retrieve it. Core Data isn’t technically a database, although it usually stores its data in one (an SQLite database, to be precise). It’s not an object-relational mapper (ORM), though it can feel like one. It’s truly an object graph, allowing you to create, store, and retrieve objects that have attributes and relationships to other objects. Its simplicity and power allow you to persist data of any form, from basic data models to complex.

This sounds very straightforward, but at the beginning Core Data is very complex to use though. But it’s worth the learning effort because Core Data provides you a lot of possibilities. For example, you can perform undo and redo operations. It’s also very performant and Core Data lazy loads the data.

From my experience as an iOS developer, I've used CoreData a lot of times and came up with a library that allows you to handle most of the situations with much less code than using the raw CoreData methods. If you would like to know more, please 