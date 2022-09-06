链接：https://blog.csdn.net/kongtaoxing/article/details/124415898

最近做OJ试题的时候，做到了一道需要很大数组的题，看着代码没有问题，但是在VS2019上就是不能通过，提示错误：**0x00B22E97 处有未经处理的异常(在 Project3.exe 中): 0xC00000FD: Stack overflow** ![报错截图](https://img-blog.csdnimg.cn/21c6a2788d31460abfe9183b8436a7e6.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5rab6KGM,size_20,color_FFFFFF,t_70,g_se,x_16)经过一段时间地研究，我发现OJ上对代码运行的空间限制是64Mb，而VS2019新工程项目默认运行空间限制是1Mb，因此通过修改项目设置，最终成功运行程序。具体修改方式如下：
依次点击 **项目-属性-链接器-系统-堆栈保留大小**
![在这里插入图片描述](https://img-blog.csdnimg.cn/ab68292735c9411eb2d1ef01416edf23.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5rab6KGM,size_20,color_FFFFFF,t_70,g_se,x_16)
![在这里插入图片描述](https://img-blog.csdnimg.cn/e99552b2404a487380ffaf99d363eadb.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5rab6KGM,size_20,color_FFFFFF,t_70,g_se,x_16)
可以看到默认堆栈保留大小为1Mb，将其数据修改为**67108864**（64\*1024*1024，即64Mb，可根据题目要求自行修改）后保存，然后再次运行程序，就能成功运行啦！
