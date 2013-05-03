srt.js
======

SubRip (.srt) parser and stringifier. This is the SRT parser we use for [Animite](http://github.com/vas/animite). NodeJS compatible!

##Usage

```javascript

// initialize
var srt = new SRT();

// parse an .srt (SubRip) file into an object
var json = srt.parse( file );

// re-encode to SubRip string
var string = srt.stringify( json );
```

The JSON structure of the SRT is the following:

```javascript

json = [ // array of subtitles
	{ 
		id : 1, // subtitle number (usually array index + 1)

		time : { // time object
			start : 0,   // start time in seconds
			end : 10,    // end time in seconds
			duration : 0 // difference (end-start)
		},

		content : [
			"Winter is coming.", // each array element is an .srt "\n"
			"You keep saying that..."
		]
	}
]

```

For quick use, just use:

```javascript
var srt = new SRT(file); // will automatically return parsed .srt
```
