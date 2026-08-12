---
id: troubleshooting-hik-connect-preview-streaming
title: Hik-Connect Preview Streaming Troubleshooting
order: 10
---

Hik-Connect preview streaming mainly uses two methods: direct device streaming and media server relay streaming.

When preview fails, loads slowly, or shows messages such as "unstable network", first confirm how the device was added and which streaming method is actually being used, and then troubleshoot accordingly.

## Direct Device Streaming

In direct mode, the video stream is transmitted directly from the device to Hik-Connect.

### Device Stream Abnormality

The device may be unable to output the video stream normally, or the recorder may not have successfully accessed the corresponding stream from the front-end camera.

Use clients such as iVMS-4200 for cross testing. If the same issue also occurs on other clients, check the device-side stream first.

A common case is sub-stream abnormality. Switch between main stream and sub-stream in Hik-Connect for testing:

- Main stream previews normally, but sub-stream cannot preview: focus on checking the sub-stream configuration and access status.
- Both main stream and sub-stream cannot preview: further check the device output and network environment.

Recommended actions:

1. Check the stream access status of the device and front-end camera, and confirm whether local preview works normally.
2. Upgrade the device to the currently recommended latest firmware version to exclude known issues in older versions.
3. Check device port 554. If direct streaming is performed through a public IP address, confirm that the related ports are correctly mapped.

### Network Abnormality

Network issues are one of the common causes of preview failure. The issue may involve either the device-side network or the mobile phone-side network.

Check whether other devices on the same network have the same symptom. If multiple devices have issues in the same network environment, check the network environment first.

Recommended actions:

1. Check whether there are port, firewall, or other access restrictions on the device-side network.
2. Test with a different mobile phone network, such as switching between Wi-Fi and mobile data.
3. If possible, test with a different device-side network for comparison.

### App-Side Abnormality

If the device can output the stream normally and network communication is normal, but Hik-Connect still cannot preview normally, the issue may involve App-side compatibility or decoding.

Recommended actions:

1. Upgrade the Hik-Connect App to the latest version.
2. If the issue persists, collect the device model, firmware version, App version, device adding method, and specific error information for further analysis.

## Media Server Relay Streaming

In media server mode, the device video stream is forwarded through the server and then sent to the Hik-Connect App.

Compared with direct mode, the network path is longer, so the device status, network environment, and App-side condition can all affect preview.

### Device-Side Issues

#### Some Devices Have Streaming Method Limitations

Some older models or devices that only support Hik-Connect Domain may not preview normally through P2P.

Recommended action:

Configure port mapping according to device support, configure DDNS in the Hik-Connect App, and test through direct connection.

#### Device Stream Push Abnormality

The device may have an abnormality when outputting the video stream.

Recommended actions:

1. Restart the device.
2. Upgrade the device to the currently recommended latest firmware version.

#### Device Cloud Service Connection Abnormality

If the connection between the device and the cloud service is abnormal, preview may fail or the App may show messages such as "unstable network".

Recommended actions:

1. Restart the device so that it reconnects to the cloud service.
2. Check the stability of the device-side network and related network access restrictions.

#### Other Device Abnormalities

If the issue persists, further check the device running status and video stream configuration.

Recommended actions:

1. Check local preview and device running status.
2. Check the video stream access status of the device.
3. Focus on confirming whether the sub-stream parameters are correct and whether the recorder can obtain the corresponding sub-stream normally.

### Network Issues

#### Poor Network Quality

Media server streaming involves multiple network segments between the device, server, and mobile phone. Poor quality on any segment may cause streaming failure, slow loading, or preview interruption.

Recommended actions:

If site conditions allow:

1. Configure necessary port mapping for the device.
2. Configure DDNS in the Hik-Connect App.
3. Test through direct connection.

Direct connection testing can help determine whether the issue is related to the media server relay path or the related network environment.

#### Network Access Restrictions

If the device-side network has firewall, port, or other access restrictions, normal communication between the device and Hik-Connect services may be affected.

Recommended action:

Check the site firewall, router, and network policies, and confirm that the network connections required by the device are not restricted.

### App-Side Issues

#### Video Decoding Abnormality

In some cases, the App has already received the video stream, but decoding may still fail due to encoding compatibility, abnormal stream data, or missing key frames.

Recommended actions:

1. Upgrade the Hik-Connect App to the latest version.
2. Change the video encoding format to H.264 for testing.
3. Temporarily disable advanced encoding functions such as Smart encoding for testing.
4. Check the I-frame interval setting. In general, set it according to the actual frame rate. For example, in a 25 fps scenario, try setting it to 25.

#### Account Region and Usage Region Are Different

If the service region of the Hik-Connect account is different from the user's actual usage region, the connection experience may be affected.

Recommended action:

Use a Hik-Connect account and service region that match the user's actual region, and then test preview again.

#### Other Cases

If the issue persists after completing the above troubleshooting, provide the following information for further analysis:

- Device model
- Device serial number
- Current firmware version
- Hik-Connect App version
- Mobile phone model and operating system version
- Device adding method
- Main stream and sub-stream test results
- Specific error information or screenshots
- Issue occurrence time and reproduction frequency
- Device-side and mobile phone-side network environments
