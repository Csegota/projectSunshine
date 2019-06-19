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
- Class that sits between an application and its data source. Job is to provides easily managed access to underlying data source. Allows for applications to share/access data between one another.
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


