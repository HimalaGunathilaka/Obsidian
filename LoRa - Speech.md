So, as my friend Sasindu mentioned, LoRa is used for long range communication. But have you ever wondered how it worked under the hood?
Let me introduce you to chirps.
A chirp is a signal where the frequency increases or decreases over time kind of like a chirp of a bird, smooth and continous.
In LoRa we use two types of chirps, 
- up-chirp where frequency increases over time and 
- down-chirp where frequency decreases over time.
So, what so special about chirp? 
Well, it's how we use them that makes LoRa unique.
First we send few up-chirps followed by two down-chirps to establish a synchronization.
After that, to send data we use up-chirps. Each up-chirp is shifted forward in time to represent different symbols. The delay 
Why do it this way? Well imagine part of the signal was lost on air, and only part came to the receiver. Don't worry lora only use the delay it take for a certain frequency to come. So, even if a part is missing lora can still understand what symbol that was.
Moving on, here you can see some graph on Spreading factor. Spreading factor is the number of bits used to encode each symbol. 
Increasing the spreading factor will increase the time on air, and more time on air mean less bit per second will be transmitted. Why do we do that then? Well longer time on air means that there is a high chance the receiver receives it. 
We talk about the super powers of lora, but there are disadvantages to i as well. Mainly it has a low data transmission rate, it can be interfere by large objects as you seen in the video, and lora isn't designed as a reliability on mind. I mean like it doesn't acknowledge a message was sent or not.
So yeah thats it.
Hoped you enjoyed our presentation.