# Get User Media(GUM) for OBS

The OBS Browser Source doesn't support direct access to media like Camera, Microphone, Desktop Capture, Midi and Game Controllers. 
The Get User Media for OBS sends media from a Chrome Browser to the OBS Browser source. 
```mermaid
graph LR;
subgraph um[User Media]
  direction LR
m[DesktopCapture,
  Microphone,
  Midi,
  Gamepad];
end

subgraph MediaPipe
  direction LR
  MPa(Video and Text\nAnalysis);
end

C(GUM for OBS)
um--> C;
MediaPipe-->C;
C ---> |WebRTC|B(OBS Browser);
C ---> |WebSocket|B;

subgraph OBS
B(Browser Source);
end
```

## Getting Started
Open [GUM for OBS](https://obsgum.github.io/) in a Chrome browser.  
Optionally, download and run GUM for OBS locally.  
> :memo: **Note:** The WebSpeech API doesn't work locally.  Google annouced at I/O 2024 that local WebSpeech is coming soon. 

### Enable the OBS WebSocket Server. 
Open [OBS](https://obsproject.com/).
1. In the menu bar click Tools --> WebSocket Server Settings
2. Check the box to "Enable WebSocket Server"
3. Click the "Show Connect Info" button
4. copy the password

### Connect to the OBS WebSocket Server
<p><img src="https://github.com/OBSGUM/obsgum.github.io/assets/169208894/9d4747c9-7c7e-4d0e-96f2-f1e5b0290cd9" width="400" ></p>
On the GUM for OBS page enter the OBS WebSocket Server details in the IP address, Port Number and Password fields. 
Click the "Connect to OBS" button.  If the connection is successful the button color will turn to green. 

## Add an OBS Scene and Source
1. Create a Scene named "Scene"
2. Add a Video Capture Device source

![image](https://github.com/UUoocl/OBS-face-tracking-with-P5js/assets/99063397/a136b9a3-7225-4079-95ec-14adef4bca83)

3.Open a preview window
  - right click on the "Video Capture Device" source
  - click "Windowed Projector (Source)"
  - ![image](https://github.com/UUoocl/OBS-face-tracking-with-P5js/assets/99063397/8e0432a7-4660-4e0c-8933-8aaae338d1b4)

