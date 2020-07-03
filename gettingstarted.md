# Getting Started

Let's get you started in 5 minutes \(reading doesn't count!\). We will switch on an LED connected to your Arduino using the Blynk App on your smartphone.

Connect an LED as shown here:

![](.gitbook/assets/Arduino_LED.jpg)

## Getting Started With The Blynk App

### 1. Create a Blynk Account

After you download the Blynk App, you'll need to create a New Blynk account. This account is separate from the accounts used for the Blynk Forums, in case you already have one.

We recommend using a **real** email address because it will simplify things later.

![](.gitbook/assets/register_account.png)

#### Why do I need to create an account?

An account is needed to save your projects and have access to them from multiple devices from anywhere. It's also a security measure.

You can always set up your own [Private Blynk Server](./#blynk-server) and have full control.

### 2. Create a New Project

After you've successfully logged into your account, start by creating a new project.

![](.gitbook/assets/create_project_button.png)

### 3. Choose Your Hardware

Select the hardware model you will use. Check out the [list of supported hardware](./#supported-hardware)!

![](.gitbook/assets/select_hardware.png)

### 4. Auth Token

**Auth Token** is a unique identifier which is needed to connect your hardware to your smartphone. Every new project you create will have its own Auth Token. You'll get Auth Token automatically on your email after project creation. You can also copy it manually. Click on devices section and selected required device :

![](.gitbook/assets/token_1.png)

And you'll see token :

![](.gitbook/assets/new_device.png)

**NOTE:** Don't share your Auth Token with anyone, unless you want someone to have access to your hardware.

It's very convenient to send it over e-mail. Press the e-mail button and the token will be sent to the e-mail address you used for registration. You can also tap on the Token line and it will be copied to the clipboard.

Now press the **"Create"** button.

![](.gitbook/assets/new_project.png)

### 5. Add a Widget

Your project canvas is empty, let's add a button to control our LED.

Tap anywhere on the canvas to open the widget box. All the available widgets are located here. Now pick a button.

**Widget Box**

![](.gitbook/assets/widgets_box.png)

**Drag-n-Drop** - Tap and hold the Widget to drag it to the new position.

**Widget Settings** - Each Widget has it's own settings. Tap on the widget to get to them.

![](.gitbook/assets/button_settings.png)

The most important parameter to set is **PIN** . The list of pins reflects physical pins defined by your hardware. If your LED is connected to Digital Pin 8 - then select **D8** \(**D** - stands for **D**igital\).

![](.gitbook/assets/pin_selection.png)

### 6. Run The Project

When you are done with the Settings - press the **PLAY** button. This will switch you from EDIT mode to PLAY mode where you can interact with the hardware. While in PLAY mode, you won't be able to drag or set up new widgets, press **STOP** and get back to EDIT mode.

You will get a message saying "Arduino UNO is offline". We'll deal with that in the next section.

![](.gitbook/assets/play_button.png)

## Getting Started With Hardware

### How To Use an Example Sketch

You should by now have the Blynk Library installed on your computer. If not - [click here](./#downloads-blynk-library).

Example sketches will help you get your hardware online quickly and major Blynk features.

Open the example sketch according to the hardware model or shield you are using.

![](.gitbook/assets/connection_type_sketch.png)

Let's take a look at the example sketch for an [Arduino UNO + Ethernet shield](https://github.com/blynkkk/blynk-library/blob/master/examples/GettingStarted/BlynkBlink/BlynkBlink.ino)

```cpp
#define BLYNK_PRINT Serial
#include <SPI.h>
#include <Ethernet.h>
#include <BlynkSimpleEthernet.h>

char auth[] = "YourAuthToken";

void setup()
{
  Serial.begin(9600); // See the connection status in Serial Monitor
  Blynk.begin(auth);  // Here your Arduino connects to the Blynk Cloud.
}

void loop()
{
  Blynk.run(); // All the Blynk Magic happens here...
}
```

### Auth Token

In this example sketch, find this line:

```cpp
char auth[] = "YourAuthToken";
```

This is the [Auth Token](./#getting-started-getting-started-with-application-4-auth-token) that you emailed yourself. Please check your email and copy it, then paste it inside the quotation marks.

It should look similar to this:

```text
char auth[] = "f45626c103a94983b469637978b0c78a";
```

Upload the sketch to the board and open Serial Terminal. Wait until you see something like this:

```text
Blynk v.X.X.X
Your IP is 192.168.0.11
Connecting...
Blynk connected!
```

**Congrats! You are all set! Now your hardware is connected to the Blynk Cloud!**

## Blynking

Go back to the Blynk App, push the button and turn the LED on and off! It should be Blynking.

![](.gitbook/assets/button_pressed.png)

Check out [other example sketches](https://github.com/blynkkk/blynk-library/tree/master/examples).

Feel free to experiment and combine different examples together to create your own amazing projects.

For example, to attach an LED to a [PWM](http://www.arduino.cc/en/Tutorial/Fading)-enabled Pin on your Arduino, set the slider widget to control the brightness of an LED. Just use the same steps described above.

