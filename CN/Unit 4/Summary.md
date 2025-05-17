
1. **TCP Window Management:** Controls how much data can be sent before receiving an acknowledgment to optimize flow and avoid congestion.

2. **Sliding Window:** Sender moves the window forward after acknowledgments to send new data continuously.

3. **Flow Control:** Prevents sender from overwhelming receiver by matching send rate with receiver’s processing capacity.

4. **Congestion:** Network overload when demand exceeds capacity, causing delays and packet loss.

5. **Congestion Control:** Techniques to prevent or alleviate congestion via open-loop (prevention) and closed-loop (reaction) methods.

6. **Quality of Service (QoS):** Measures network performance based on reliability, delay, jitter, and bandwidth.

7. **QoS Requirements by Application:** Different apps need varying levels of bandwidth, delay, jitter, and loss tolerance.

8. **Leaky Bucket Algorithm:** Controls traffic flow by releasing packets at a fixed rate, discarding excess when overloaded.

9. **Techniques to Improve QoS:** Includes over-provisioning, buffering, scheduling, and traffic shaping for better network performance.

10. **TCP Congestion Control:** Uses congestion window and phases (slow start, avoidance, detection) to manage traffic flow.

11. **TCP Congestion Control Phases:** Slow start ramps up sending rate exponentially, then congestion avoidance increases linearly.

12. **Threshold:** The point where TCP shifts from slow start to congestion avoidance to prevent overload.

13. **Maximum Capacity:** The network’s bandwidth limit that TCP tries to approach without causing congestion.

