# Computer Networks Assignment 3

1. The objective of this assignment was to design a TCP protocol capable of downloading and uploading reliably while dealing with congestion efficiently
2. The server was implemented as a leaky bucket, every time we sent a request our tokens would get consumed, if our bucket became empty we would get squished and get penalised.
3. The server would also randomly drop packets, designed to simulate a real time network.
4. So we had to modify the rate of sending requests adaptively based on various metrics like EWMA RTT, Last squish time to optimise for speed while maintaining reliability.

## Strategies Implemented
* Having separate threads for sending and receiving packets
* Tweaking the sleep time between sending consecutive requests based on the measured response time i.e (Expontentially Weighted Moving Average) which represents the current state of server responses.
* Sending requests in bursts and adaptively changing burst size
* Since the server was dropping packets randomly even when squishing wasn't present, so only going into cautious mode if the measured rate of dropping became higher than a threshold.
