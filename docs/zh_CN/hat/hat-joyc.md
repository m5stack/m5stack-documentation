# JoyC

<el-tag effect="plain">SKU:U079</el-tag>

<div class="product_pic"><img src="assets\img\product_pics\hat\JoyC_hat\JoyC_01.webp"><img src="assets\img\product_pics\hat\JoyC_hat\JoyC_02.webp"></div>

## 描述

**JoyC** 是一款专为M5StickC设计的摇杆模块，可进行双手操作.内嵌STM32F030F4主控芯片，采用I2C通信协议与主机M5StickC进行数据传输.摇杆的范围为0~200，左右摇杆下方各有12颗RGB LED,摇杆底部配有16340电池底座，提供长时间续航.该摇杆支持进行全方位的角度偏移与中心按压，并输出角度偏移数据以及开关数字信号.

## 产品特性

- 内嵌STM32F030F4
- 通信协议：I2C（地址：0x38）
- 支持全方位偏移/中心按键

## 包含

- 1x JoyC
- 1x 16340电池(700mAh)

## 应用

- 游戏控制器
- 无线摇杆设备

## 规格参数

<table>
   <tr style="font-weight:bold">
      <td>规格</td>
      <td>参数</td>
   </tr>
   <tr>
      <td>通信协议</td>
      <td>I2C：0x38</td>
   </tr>
   <tr>
      <td>净重</td>
      <td>81g</td>
   </tr>
   <tr>
      <td>毛重</td>
      <td>117g</td>
   </tr>
   <tr>
      <td>产品尺寸</td>
      <td>100*55*50mm</td>
   </tr>
   <tr>
      <td>包装尺寸</td>
      <td>119*89*65mm</td>
   </tr>
 </table>

## EasyLoader

<img src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/image/EasyLoader_M5StickC_logo.webp" width="100px" style="margin-top:20px">

<a href="https://m5stack.oss-cn-shenzhen.aliyuncs.com/EasyLoader/Windows/HAT/EasyLoader_JoyC_Test.exe"><el-button type="primary">单独使用</el-button></a>

<a href="https://m5stack.oss-cn-shenzhen.aliyuncs.com/EasyLoader/Windows/HAT/RoverC_Remote/RoverC%26JoyC_Remote.zip"><el-button type="primary">RoverC搭配JoyC使用</el-button></a>

>1.EasyLoader是一个简洁快速的程序烧录器，每一个产品页面里的EasyLoader都提供了一个与产品相关的案例程序，通过简单步骤将其烧录至主控，能够进行一系列的功能验证.

>2.下载软件后，双击运行应用程序，将M5设备通过数据线连接至电脑,选择端口参数，点击 **"Burn"** 即可开始烧录.(**为M5StickC烧录时，请将波特率设置在750000或115200**)


## 通讯协议

- 协议类型I2C
- I2C Address: **0x38**                                       

```clike
/*--------------------------------------------------------------------------------------------------*/
| JOYC_COLOR_REG       | 0x20
| ------------------------------------------------------------------------------------------------
| rgb_r_reg[0]  |  R/W  |  RED value
| rgb_g_reg[1]  |  R/W  |  Green value
| rgb_b_reg[2]  |  R/W  |  Blue value
/*----------------------------------------------------------------------------------------------------

/*--------------------------------------------------------------------------------------------------*/
| JOYC_LEFT_X_REG       | 0x60
| ------------------------------------------------------------------------------------------------
| left_x_reg[0]  |  R  |  LEFT X VALUE
/*----------------------------------------------------------------------------------------------------

/*--------------------------------------------------------------------------------------------------*/
| JOYC_LEFT_Y_REG       | 0x61
| ------------------------------------------------------------------------------------------------
| left_y_reg[0]  |  R |  LEFT Y VALUE
/*----------------------------------------------------------------------------------------------------

/*--------------------------------------------------------------------------------------------------*/
| JOYC_RIGHT_X_REG       | 0x62
| ------------------------------------------------------------------------------------------------
| right_x_reg[0]  |  R |  RIGHT X VALUE
/*----------------------------------------------------------------------------------------------------

/*--------------------------------------------------------------------------------------------------*/
| JOYC_RIGHT_Y_REG       | 0x63
| ------------------------------------------------------------------------------------------------
| right_y_reg[0]  |  R  |  RIGHT Y VALUE
/*----------------------------------------------------------------------------------------------------

/*--------------------------------------------------------------------------------------------------*/
| JOYC_PRESS_REG       | 0x64
| ------------------------------------------------------------------------------------------------
| press_reg[0]  |  R  |  LEFT AND RIGHT PRESS VALUE
                           | 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 |
                           | R | R | R | R | R | R | LEFT | RIGHT |
                           | LEFT: 
                                   Pressed: 1
                                   Released: 0
                           | RIGHT: 
                                   Pressed: 1
                                   Released: 0
/*----------------------------------------------------------------------------------------------------

/*--------------------------------------------------------------------------------------------------*/
| JOYC_LEFT_ANGLE_REG       | 0x70
| ------------------------------------------------------------------------------------------------
| left_angle_reg[0]  |  R |  LEFT ANGLE VALUE
/*----------------------------------------------------------------------------------------------------

/*--------------------------------------------------------------------------------------------------*/
| JOYC_RIGHT_ANGLE_REG       | 0x72
| ------------------------------------------------------------------------------------------------
| right_angle_reg[0]  |  R |  RIGHT ANGLE VALUE
/*----------------------------------------------------------------------------------------------------

/*--------------------------------------------------------------------------------------------------*/
| JOYC_LEFT_DISTANCE_REG       | 0x74
| ------------------------------------------------------------------------------------------------
| left_distance_reg[0]  |  R |  LEFT DISTANCE VALUE
/*----------------------------------------------------------------------------------------------------

/*--------------------------------------------------------------------------------------------------*/
| JOYC_RIGHT_DISTANCE_REG       | 0x76
| ------------------------------------------------------------------------------------------------
| right_distance_reg[0]  |  R  |  RIGHT DISTANCE VALUE
/*----------------------------------------------------------------------------------------------------

```

## 案例程序

### 1. Arduino

配合RoverC使用 [点击此处](https://github.com/m5stack/M5-ProductExampleCodes/tree/master/Hat/JoyC/Arduino/JoyC)，获取完整程序.

单独使用 [点击此处](https://github.com/m5stack/M5StickC/blob/master/examples/Hat/JoyC/JoyC.ino)，获取完整程序.

### 2. UIFlow

- [请点击此处获取UIFlow示例](https://github.com/m5stack/M5-ProductExampleCodes/tree/master/Hat/JoyC/UIFlow)

<img src="assets\img\product_pics\hat\JoyC_hat\JoyC.webp" width="50%" height="50%"> 


## 相关视频

<video class="video_size" controls>
    <source src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/video/Product_example_video/HAT/JoyC.mp4" type="video/mp4">
</video>

<script>

   var purchase_link = 'https://m5stack.com/collections/m5-hat/products/joyc-w-o-m5stickc';


   anchor_search(purchase_link);
   scrollFunc();

</script>