# Computer Networks Assignment 3

1. The objective of this assignment was to design a TCP protocol capable of downloading and uploading reliably while dealing with congestion efficiently
2. The server was implemented as a leaky bucket, everytime we sent a request our tokens would get consumed, if our bucket became empty we would get squished and get penalised
3. So we had to modify the rate of sending requests adaptively based on various metrics like EWMA RTT, Last squish time to optimise for speed while maintaining reliability.
