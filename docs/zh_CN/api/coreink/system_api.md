# System & Button & RTC

## begin()

**函数原型：**

`int begin(bool InkEnable = true, bool wireEnable = false);`

**功能：初始化 E-Ink ，RTC , I2C , Speaker**


**例程**

```arduino
#include "M5CoreInk.h"

void setup() {
  M5.begin(true,false);
}
```

## update()

**函数原型：**

`void update();`

**功能：刷新设备按键/蜂鸣器状态**

**例程：**
```arduino

if( M5.BtnPWR.wasPressed())
{
  Serial.printf("Btn wasPressed!");
}
M5.update();

```

## Button

**功能：检测设备按键状态**

`M5.BtnUP.wasPressed()`

`M5.BtnDOWN.wasPressed()`

`M5.BtnMID.wasPressed()`

`M5.BtnEXT.wasPressed()`

`M5.BtnPWR.wasPressed()`

?>RTC相关函数使用前请使用`M5.begin();`进行初始化

## Speaker

**功能：蜂鸣器驱动**

`void end();`

`void mute();`

`void tone(uint16_t frequency);`

`void tone(uint16_t frequency, uint32_t duration);`

`void beep();`

`void setBeep(uint16_t frequency, uint16_t duration);`

`void update();`

`void write(uint8_t value);`

`void setVolume(uint8_t volume);`

`void playMusic(const uint8_t *music_data, uint16_t sample_rate);`


```
M5.Speaker.tone(2700);
```

## SetTime()

**函数原型:**

`void SetTime(RTC_TimeTypeDef* RTC_TimeStruct)`

**函数参数:**

设置结构体变量时间


## GetTime()

**函数原型:**

`void GetTime(RTC_TimeTypeDef* RTC_TimeStruct)`

**函数参数:**

获取结构体时间


## SetData()

**函数原型:**

`void SetData(RTC_TimeTypeDef* RTC_DateStruct)`

**函数参数:**

设置结构体变量日期


## GetData()

**函数原型:**

`void GetData(RTC_TimeTypeDef* RTC_DateStruct)`

**函数参数:**

获取结构体变量日期

**使用示例:**

```
#include "M5CoreInk.h"

Ink_Sprite InkPageSprite(&M5.M5Ink);

RTC_TimeTypeDef RTCtime;
RTC_DateTypeDef RTCDate;

char timeStrbuff[64];

void flushTime(){
    M5.rtc.GetTime(&RTCtime);
    M5.rtc.GetData(&RTCDate);
    
    sprintf(timeStrbuff,"%d/%02d/%02d %02d:%02d:%02d",
                        RTCDate.Year,RTCDate.Month,RTCDate.Date,
                        RTCtime.Hours,RTCtime.Minutes,RTCtime.Seconds);
                                         
    InkPageSprite.drawString(10,100,timeStrbuff);
    InkPageSprite.pushSprite();
}

void setupTime(){
  
  RTCtime.Hours = 23;
  RTCtime.Minutes = 33;
  RTCtime.Seconds = 33;
  M5.rtc.SetTime(&RTCtime);
  
  RTCDate.Year = 2020;
  RTCDate.Month = 11;
  RTCDate.Date = 6;
  M5.rtc.SetData(&RTCDate);
}

void setup() {

    M5.begin();
    if( !M5.M5Ink.isInit())
    {
        Serial.printf("Ink Init faild");
        while (1) delay(100);   
    }
    M5.M5Ink.clear();
    delay(1000);
    //creat ink refresh Sprite
    if( InkPageSprite.creatSprite(0,0,200,200,true) != 0 )
    {
        Serial.printf("Ink Sprite creat faild");
    }
    setupTime();
}

void loop() {
  flushTime();
  delay(15000);
}
```
