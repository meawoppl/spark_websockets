spark_websockets
================

Websockets implementation for Spark Core, ported from Arduino WebSocketClient



How to use :
==============
```
#include "websocketclient.h"

WebSocketClient client;
char server[] = "echo.websocket.org";

void onMessage(WebSocketClient client, char* message) {
  Serial.print("Received: ");
  Serial.println(message);
}

void setup() {
  Serial.begin(9600);
  client.connect(server);
  client.onMessage(onMessage);
  client.send("Hello World!");
}

void loop() {
  client.monitor();
}

```
