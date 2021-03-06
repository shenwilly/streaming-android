# Shared Object Streamless Test

This example builds off the [SharedObjectTest](../SharedObjectTest) example, yet, instead of relying on establishing a connection to a Shared Object based on a previously established RTSP connection through a Stream, it utilizes the `startDataOnlyStream` method of the `R5Connection` instance to connect to a Shared Object without a Stream:

```java
R5Configuration config = new R5Configuration(R5StreamProtocol.RTSP,
        TestContent.GetPropertyString("host"),
        TestContent.GetPropertyInt("port"),
        TestContent.GetPropertyString("context"),
        TestContent.GetPropertyFloat("publish_buffer_time"));
config.setLicenseKey(TestContent.GetPropertyString("license_key"));
config.setBundleID(b);

connection = new R5Connection(config);

connection.addListener(this);
connection.startDataOnlyStream()
```

> Please refer to the [SharedObject](../SharedObject) example for using the Shared Object API for connection and method and property handling.
