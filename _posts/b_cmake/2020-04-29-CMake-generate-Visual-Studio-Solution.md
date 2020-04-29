# CMake generate Visual Studio Project

1. Set environment for vs on cmd，change directory to `Build` directory in you Visual Studio installation directory

   `cd "disk_name:\Program Files (x86)\Microsoft Visual Studio\2019\Professional\VC\Auxiliary\Build"`

2. run bat `vcvarsall.bat` for 64 bit architecture.

   `./vcvarsall.bat x64`

3. Generate Visual Studio Project

   `cmake -G "Visual Studio 16 2019"`

> If you need another Visual Studio Project version,  you cant run **cmake -G** on the cmd, it will print all of the Project version.



1. 设置vs环境变量， 进入 vs 安装目录下的build文件夹中

   `cd "disk_name:\Program Files (x86)\Microsoft Visual Studio\2019\Professional\VC\Auxiliary\Build"`

2. 运行 bat 脚本 `vcvarsall.bat`,  `x64` 是编译64位系统的软件

   `./vcvarsall.bat x64`

3. 生成 vs 项目， 至此， 会生成一个 vs 项目

   `cmake -G "Visual Studio 16 2019"`

4. 如果想要生成 nmake 项目，可以运行如下命令

   `cmake -G "NMake Makefiles"`

   `nmake`

> 如果你需要其他版本的 vs 项目，你可以在命令行中运行 **cmake -G** 来查看相应的名称。