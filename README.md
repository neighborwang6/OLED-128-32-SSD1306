# OLED-128-32-SSD1306
#基于SSD1306的OLED模块的I2C驱动，字库，“图片”等
   1、SSD1306的(128*32)尺寸的OLED模块驱动时候，每写一次命令时候都要发动Commend数据帧。
      a.Co位在发送命令之前需要设为‘1’
      b.Co位在决定下一帧发送数据时候设为‘0’
   2、写数据时候则是指针自动加一的。在发送像素数据过程中，如果想重新发送命令时候需要重复起始。
   3、像素数据：
      a.page模式下一个“像素条”由4个像素条组成（128*64尺寸的屏幕一个像素条由8个像素组成）。
      b.每一个“像素条”需要一个字节的数据驱动。
      c.这个四个像素的像素条的有效数据来自于这个字节的第1，3，5，7bit。
