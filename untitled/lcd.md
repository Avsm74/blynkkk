# LCD

This is a regular 16x2 LCD display made in our secret facility in China. It can work in 2 modes :

* Simple
* Advanced

## Simple mode

In simple mode your LCD widget performs as regular widget with Frequency reading.

With Frequency Reading mode you need to select update interval and application will trigger events with required timing. Your application should be open and running in order to make requests to hardware. You don't need any code for Analog and Digital pins in that case. However for virtual pins you need to use next code :

```cpp
//triggered from app
BLYNK_READ(V1)
{
  //send to app
  Blynk.virtualWrite(V1, val);
}
```

In Simple mode LCD also supports formatting options.

### Formatting options

Let's assume, your sensor sends number 12.6789 to Blynk application. Next formatting options supported:

`/pin/` - displays the value without formatting \(12.6789\)

`/pin./` - displays the value without decimal part \(13\)

`/pin.#/` - displays the value with 1 decimal digit \(12.7\)

`/pin.##/` - displays the value with two decimal places \(12.68\)

**Sketch:** [LCD Simple Mode Pushing](https://github.com/blynkkk/blynk-library/blob/master/examples/Widgets/LCD/LCD_SimpleModePushing/LCD_SimpleModePushing.ino)

**Sketch:** [LCD Simple Mode Reading](https://github.com/blynkkk/blynk-library/blob/master/examples/Widgets/LCD/LCD_SimpleModeReading/LCD_SimpleModeReading.ino)

## Advanced mode

Advanced mode is for experienced users. Allows you to use special commands to control LCD.

## Commands

Init LCD variable :

```cpp
WidgetLCD lcd(V1);
```

Send message :

```cpp
lcd.print(x, y, "Your Message");
```

Where `x` is a symbol position \(0-15\), `y` is a line number \(0 or 1\),

Clear LCD :

```cpp
lcd.clear();
```

**Sketch:** [LCD Advanced Mode](https://github.com/blynkkk/blynk-library/blob/master/examples/Widgets/LCD/LCD_AdvancedMode/LCD_AdvancedMode.ino)

