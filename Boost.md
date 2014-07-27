#Windows环境下Boost安装

&emsp;&emsp;Boost库是一个可移植、提供源代码的C++库，作为标准库的后备，是C++标准化进程的开发引擎之一。

&emsp;&emsp;由于PPCA大作业的需要，需要对Boost进行安装。在这里记录下一些安装细节。

##下载

&emsp;&emsp;去官网(<a href = "www.boost.org">www.boost.org</a>)即可下载到Boost的文件了。文件只有100+MB。

在这里，我下载的是：
	
	boost_1_55_0.zip。

##编译
	
&emsp;&emsp;将压缩文件解压后，不难发现一个叫做bootstrap.bat的批处理文件，运行它即可。

###事故(1)
	
&emsp;&emsp;系统报错，显示的是：
> 'cl' 不是内部或外部命令，也不是可运行的程序或批处理文件。

&emsp;&emsp;妈蛋，这是啥。baidu之后，有了真相。原来是以前改PATH路径把很多东西删去了。

&emsp;&emsp;所以重新下载Microsoft Visual Studio，然后在PATH地址里添加cl.exe所在的文件夹。

参考资料：<a href = "http://blog.csdn.net/hmsiwtv/article/details/8155441">windows 控制台下运行cl命令</a>

##运行

&emsp;&emsp;编译完成以后，根目录下会多出一个bjam.exe的文件，运行这个文件即可。
（这个文件需要大量的运行时间，我的电脑用了20+min吧）

&emsp;&emsp;如果是要使用MinGW的话需要使用下面的命令：

	bjam.exe install toolset=gcc stage --variant=release

##调试
&emsp;&emsp;Boost的安装到此就差不多了。由于中途的事故引发的装载VS的小插曲，大概装了两个多小时吧。

&emsp;&emsp;凌晨三点啦，大家晚安。

##总体参考
* <a href = "http://blog.csdn.net/yockie/article/details/8856190">windows下boost的安装与初试</a>
* <a href = "http://public0821.iteye.com/blog/291163">mingw环境下boost库的编译和使用</a>