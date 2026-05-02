# Raspberry-Pi-5-Security-Camera
**Overview:**
Edge surveillance system enabled by Raspberry Pi 5 and USB weatherproof camera.

**Instructions for Use:**
Utilizing the same hardware stack or a similar one with a USB camera capable of .yml config,
1. Assemble the RPi5, flash OS, and plug in the camera
2. Install ffmpeg and mediamtx
3. Copy the mediamtx.yml file from this repository to your Pi in the proper path
4. Replace the username and password
5. Install Tailscale on the Pi and your viewing device
6. Initialize mediamtx service
7. Open VLC media player on the viewing device and utilize URL in the mediamtx file

**Narrative:**
This is the first project I completed! I wanted to get away from using cheap, foreign assembled devices that were likely compromising my network.

Started this project back in November 2025 when I discovered by looking at network traffic on my router that my SEHMUA cameras from Amazon were phoning home constantly to Alibaba and Aliyun servers. I understood when I purchased the cameras that the third party app, etc. were all designed around that initially, but thought that I could provide settings or isolate on a VLAN to avoid data harvesting.

At the time I also had a Spectrum router, which didn't help much as I could not console in and change any configurations at layer 2.

Ultimately, I decided to ditch the SEHMUAs entirely and see if I could make my own. I planned to do this with a ribbon camera, common with RPi's, but realized quickly that this would not be practical due to weather. I then purchased a USB camera and proceeded to configure it for Real Time Streaming Protocol (RTSP).

Moving away from using MATLAB for data analysis in college classes and a senior capstone Machine Learning project, it was enjoyable to branch out into practical coding application.

The final product, after days of troubleshooting, is a working home security camera that only I can see.

**Technical Stack:**

- Hardware: Raspberry Pi 5 8GB RAM; SVPRO Outdoor USB Camera (Waterproof)

- Networking: Tailscale (WireGuard based) for encrypted end-to-end access to RTSP stream.

- Streaming utilization: Tailscale for secure end-to-end encryption for viewing Real Time Streaming Protocol (RTSP) on Video LAN Client (VLC) and secure ssh.

**Key Takeaways:**
- Data sovereignty is possible with the right hardware, ingenuity, and persistence
- Real Time Streaming Protocol is simple and effective
- Tailscale and other services provide a means of avoiding opening ports to the open internet (security nightmare)
- Configuration required for the USB camera using .yml was difficult at first, but proved useful for providing additional layers of security

**Future Developments:**
- Local Data Redundancy/Storage: Build off RTSP to save videos and images to an external drive and view playback
- AI Computer Vision Integration: Use lightweight AI computer vision models such as OpenCV to trigger motion-captured alerts with push notifications
