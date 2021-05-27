# Julia

Docker Jenkins Integration of Julie-Julie

Initially, this readme file is more of a journal; so I can document my steps.  As this project matures, I will convert it into a document for all users, not just notes for me.  

I'm trying to move as much of my JJ project into Docker and automated scripts for fast reliable implementation.  5/26/21

Step 1:  

I'm attempting to run vosk from a docker container.  

Here is the link to Alphacep's image on Docker Hub: 

https://hub.docker.com/r/alphacep/kaldi-vosk-server

It gives this url to pull: 

docker pull alphacep/kaldi-vosk-server

Alternatively, just run:

docker run -d -p 2700:2700 alphacep/kaldi-en:latest

This will pull the latest image and start it on port 2700. In fact, this is probably best practice as you will get the newest image.  This is taking a lot longer.  I'm guessing that on the first run, it downloads the model, etc.  I'll need to look closely at the dockerfile.   

Vosk server is a different project on github than just vosk.  Here is the url:  https://github.com/alphacep/vosk-server

This url in turn directs one to the vosk documentation page:  
https://alphacephei.com/vosk/server

Clone the test code:

git clone https://github.com/alphacep/vosk-server

I create a conda environment and (optionally set up direnv):

conda create -name voskserver

conda activate voskserver

cd vosk-server

conda install websockets

cd vosk-server/websocket

./test.py test.wav

Success for step 1.

Step 2.  Get this working with my microphone:

Use conda, not pip, to install pyaudio:

conda install pyaudio

./test_microphone









