## HOW TO RUN

> To Execte a script, Goto Run > Run Script.
> 
## Table of Contents

- [Dialogs](#)
- [Text to Speech](#)
- [Bluetooth](#)
- [WIFI](#)



## Dialogs
 
 #### Alert dialog
```javascript
let message = "Hello World!";
nts.dialog.alert(message);
```
> A basic alert with  a message.

## Text to Speech
>  

#### TTS Basic
```Javascript
let msg = 'Welcome to N8VShell!';
await tts.speak(msg);
```

#### TTS Advanced
```Javascript
let msg = 'The quick brown fox jumps over the lazy dog.';
let ttsPitch = 0.75; // Defaults to 0.75
let ttsRate = 1.0;   // Defaults to 0.9

await tts.speak(msg, ttsRate, ttsPitch);
```

#### TTS with a Custom Voice Identity
```Javascript
let sMsg = 'The quick brown fox jumps over the lazy dog.';

// Get available text to speech voice packs.
let aVoices = await tts.getVoices();

// Show the number of available voice packs.
nts.dialog.alert('Found ' + aVoices.length  + ' installed voice packs!');
```
Simulate  a conversation 
```Javascript
const dialogue = [
	{
		text: "Excuse me, what is the date and time?",
		identity: 'en-au-x-auc-local',
		pitch: 0.75,
		rate: 1.0,
	},
	{
		text: "It is " + new Date() + ' at the moment.',
		identity: 'en-au-x-auc-local',
		pitch: 0.75,
		rate: 1.0,
	},
	{
		text: "Thank you kind sir!",
		identity: 'en-au-x-auc-local',
		pitch: 0.75,
		rate: 1.0,
	}
]

// Loop through the dialog array to simulate a conversation.
dialogue.forEach((obj) => 
	await tts.speak(
	    obj.text,
	    obj.pitch,
	    obj.rate,
	    obj.identity
));

nts.dialog.alert('Done!');
```

### Bluetooth
- [Get Bluetooth State](#)
- [Toggle Bluetooth State](#)
- [Open Bluetooth Settings](#)
-  [Scan for Devices](#)
- [Pair a device]()
