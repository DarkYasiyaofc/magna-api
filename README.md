# magna-dl API
![yts.mx](https://raw.githubusercontent.com/DarkYasiyaofc/FROZEN-HARD/main/IMAGES/yts.mx.png)  
  
    

Unofficial API wrapper for yts.mx/magna-dl
## Example
The Following Code snipet will help you understand how to use this.

```js
var Magna = require("dark-yasiya-magna-api");
var magna = new Magna();
await magna.login("email@example.com","password");
await magna.addMagnet("magnet_link");
// Starts downloading, wait till that happens
var contents = await magna.getVideos();
// An object containing list of all files and folders
```

## Documentation

### Logging in

There are two ways to login, that is,

* using username and password
* using device code

the username and password method returns a token with short lifetime while device id method returns a 1 year lifetime token.

```js
var Magna = require("dark-yasiya-magna-api");
var magna = new Magna();
await magna.login("email@example.com","password");
```


```js
var Magna = require("dark-yasiya-magna-api");
var magna = new Magna();
await magna.getDeviceCode();
// prints a device code and user code, go to devices and add user code
// after adding user code, pass the device code parameter to getToken function

await magna.getToken("device_code");
// returns a token with 1 year lifetime
```

** using an old token to log in directly **

```js
var Magna = require("dark-yasiya-magna-api");
var magna = new Magna();
await magna.addToken("token");
```
### Adding magnet link

Magnet link can be added using `addMagnet` function

```js
var Magna = require("dark-yasiya-magna-api");
var magna = new Magna();
await magna.login("email@example.com","password");

await magna.addMagnet("magnet_link");

// adds a magnet link, wait till it downloads
```

### Getting contents

To get contents (only videos), use the `getVideos` function

```js
var Magna = require("dark-yasiya-magna-api");
var magna = new Magna();
await magna.login("email@example.com","password");

await magna.getVideos();

/*
Prints Array of Arrays with file data

[
  [
    {
      "fid": 124291671, // folder id
      "id": 636235280, // file id
      "name": "File Name"
    },
    ...
  ],
  ...
]
*/
```
### Deleting contents

To delete Folders use `deleteFolder` function and to delete files, use `deleteFiles` function

```js
var Magna = require("dark-yasiya-magna-api");
var magna = new Magna();
await magna.login("email@example.com","password");

await magna.deleteFile("file_id");

await magna.deleteFolder("folder_id");
```

## Contributing

Thank you for your interest in contributing, If you feel like there's something missing or any new feature can be added, just create a PR and I will see the rest.

## Help

You can contact me on social media, Everything about me can be found [here](https://github.com/DarkYasiyaofc)

## Installation

### Requirements

* Node.Js installed

### Dev Dependencies

* Axios

## Credits

* [yts.mx](https://yts.mx) For making an excellent tool

## Contact

Contact me anywhere, just visit [my portfolio](https://github.com/DarkYasiyaofc/)

## License

This project is licensed under MIT License, See [LICENSE](/LICENSE) for more information

