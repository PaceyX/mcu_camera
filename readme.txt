本实验将实现如下功能：开机后，初始化摄像头模块（OV2640），如果初始化成功，则提示选择模式：RGB565模式，或者JPEG模式。KEY0用于选择RGB565模式，KEY1用于选择JPEG模式。

    当使用RGB565时，输出图像（固定为：UXGA）将经过缩放处理（完全由OV2640的DSP控制），显示在LCD上面。我们可以通过KEY_UP按键选择：1:1显示，即不缩放，图片不变形，但是显示区域小（液晶分辨率大小），或者缩放显示，即将1600*1200的图像压缩到液晶分辨率尺寸显示，图片变形，但是显示了整个图片内容。通过KE0Y按键，可以设置对比度；KEY1按键，可以设置饱和度；KEY2按键，可以设置特效。

    当使用JPEG模式时，图像可以设置任意尺寸（QQVGA~UXGA），采集到的JPEG数据将先存放到STM32F4的内存里面，每当采集到一帧数据，就会关闭DMA传输，然后将采集到的数据发送到串口2（此时可以通过上位机软件（串口摄像头.exe）接收，并显示图片），之后再重新启动DMA传输。我们可以通过KEY_UP设置输出图片的尺寸（QQVGA~UXGA）。通过KEY0按键，可以设置对比度；KEY1按键，可以设置饱和度；KEY2按键，可以设置特效。
    

注意：本实验需要有ALIENTEK OV2640摄像头模块才可以做！！


               	正点原子@ALIENTEK
               	2014-10-25
		广州市星翼电子科技有限公司
                电话：020-38271790
                传真：020-36773971
	       	购买： http://shop62057469.taobao.com
                公司网站：www.alientek.com
         	技术论坛：www.openedv.com