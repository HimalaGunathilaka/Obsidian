- Name of the wifi -> __SSID__ 
- MAC address -> __BSSID__ 
- __Channel__ = The frequency is being divided into channels to use separately. By using it like that multiple routers can communicate in the same area of business.
- _Hard coding the wifi initials_ = Don't do that,
		Make a access point.
- Modes in esp32
	- Active
	- Deep-sleep
	- Light-sleep
![[Pasted image 20250518205136.png]]
- CPU pause -> Means the runned instructions retains and will start again when depaused.  
- ESP.deepsleep(5e6) -> $5 * 10^6$ milliseconds, (0 will be sleeping forever.)
