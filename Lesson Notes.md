# L3 - RecyclerView

* RecyclerView
		* Used to display similar data in a scrolling view. Reuses views that scroll off screen by replacing data.
* Adapter
		* Places new views when needed.
		* Used to bind data from a data source.
		* Adapter sends the view to the RecyclerView in an object called a ViewHolder
* ViewHolder
		* Contains a reference to the root view object for the item.
		* Used to cache view objects represented in the layout to make it less costly to update view with new data.
				* This way. findViewById is called only when the view is created, and not every time you want to populate the views with new data.
* Layout Manager
		* Tells the RecyclerView how to layout all of the views.

# L4 - Intents

* Intents
		* Requests that an action take place. E.g. Start new Activity, pick or display photo from phone, or making a phone call.
* Explicit Intent
		* Uses the name of the target component.
* Implicit Intent
		* Indicate an action to be done and an optional bit of data from which to execute.
		* When you dont know or care how the request will be filled. E.g. Retrieve a contact, image or number. Consider the fact for example that you dont no which app a user has specified as their default camera app.

# L5 - Android Activity Lifecycle

1. onCreate -> Created
2. onStart -> Visible
3. onResume -> Active
4. onPause -> Lost Focus
5. onStop -> Stopped
		* onDestroy -> Destroyed
		* onRestart -> Restarting -> onStart

## AsyncTask & Loaders

* Consider the situation where an activity is created and a background tasks starts to fetch data, then the divice is rotated, causing the activity to be recreated, the AsyncTask would be called then, and the original call would be sent to a zombie activity. Loaders solve this problem

Loaders
		* Provide a framework for Async loading of data. Registered by ID with a component called LoaderManager, this allows them to live beyond the lifecycle of the activity they are associated with.
		* Prevents duplicated loads from happening in parallel

# L6 - Preferences

## Data Persistence

* Saved Instance State - Key value pairs, saves state during app rotation or memory clean up. Used while user is actively using app.
* Shared Preferences class - Saves simple key value pairs to a file. Always strings, primitive. E.g. Text or numeric, user info.
Database - Save long lists of object data. E.g. Data about book suggestions.
Internal Storage / External Storage - Multimedia, audio, pictures.
Server Database - E.g. Leaderboard, Shared Network Data. Firebase, cloud DB.


# L7 - Content Providers

## 4 app components for effective Android development
1. Activities
2. Services
3. Broadcast Receivers
4. Content Providers

### Content Providers
- Class that sits between an application and its data source. Job is to provide easily managed access to underlying data source. Allows for applications to share/access data between one another.
- Reasons to use Content Providers.
	- Easily change underlying data source.
	- Leverage functionality of Android Classes. ex. Loaders
	- Allows many apps to access, use and modify your data source. Secure and managed.

- General steps for using a ContentProvider
	1. Get permission to use the ContentProvider.
	2. Get the ContentResolver
	3. Pick one of four basic actions on the data: query, insert, update, delete
	4. Identify the data you are reading or manipulating to create a URI
	5. In the case of reading from the ContentProvider, display the information in the UI


# L8 - Android Architecture Components

1. Room - SQLite object relational mapping library.
2. LiveData - Observe Changes in the DB.
3. ViewModel - Cache data that needs to survive through configuration changes (view rotation).
4. Lifecycle - To allow non-Lifecycle objects to be Lifecycle aware.

## Room
- Is and ORM - Object Relational Mapping library. Maps DB objects to Java objects.
	- Less boilerplate
	- SQL validation at compile time
	- Built to work with LiveData and RxJava for data observation.
- Main Components
	1. @Entity - To define DB tables.
	2. @DAO (Data Access Object) - To provide and API for reading and writing data.
	3. @Database - Represents a DB holder.