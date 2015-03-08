#TTS Server

This is (originally described as) a simple Text To Speech (TTS) server that run on Mac OS X. 

in truth it is an API server that should be able to support almost any command line text to speech synthesizer on any operating system that supports node.js

My goal here is to modify this code to support multiple speech synthesizers with a user-selectable audio output format.

For some reason, this code doesn't work unless you also install swagger, winston and express. I'm not sure why these are not included and will add them unless there is some legal reason why I shouldn't.

You can try the basic sample, by entering http://localhost:8082/ and entrering some text to be played.
This sample queue automatically the text entered in the fields when you modify it and will be played when you hit the play button. If you want to hear them a second time you will have to either modify the text or press the 'ReQueueAll' button before pressing Play again.

You can also use it by hitting the WebService (WS) directly:

  http://localhost:8082/api/v1/tts.json/play/Fred/Hello%20World


Will play "hello world" using the voice Fred.

Supported voice on Lion are:

   Kathy, Vicki, Victoria or Alex, Bruce, Fred

Have fun.

You can also use curl to pre-generate an audio file:
   curl -X POST -H 'Content-Type: application/json' -d '{"voice":"Alex","text":"hello world"}' 'http://localhost:8082/api/v1/tts.json/generate?api_key=node-tts-key-id'

And you can look at the REST API docs at

	http://localhost:8082/docs/
