# bounds_checking_function

#### 介绍
- 遵循C11 Annex K (Bounds-checking interfaces)的标准，选取并实现了常见的内存/字符串操作类的函数，如memcpy_s、strcpy_s等函数。
- 未来将分析C11 Annex K中的其他标准函数，如果有必要，将在该组织中实现。
- 处理边界检查函数的版本发布、更新以及维护。

#### 函数清单

- memcpy_s
- wmemcpy_s
- memmove_s
- wmemmove_s
- memset_s
- strcpy_s
- wcscpy_s
- strncpy_s
- wcsncpy_s
- strcat_s
- wcscat_s
- strncat_s
- wcsncat_s
- strtok_s
- cwcstok_s
- sprintf_s
- swprintf_s
- vsprintf_s
- vswprintf_s
- snprintf_s
- vsnprintf_s
- scanf_s
- wscanf_s
- vscanf_s
- vwscanf_s
- fscanf_s
- fwscanf_s
- vfscanf_s
- vfwscanf_s
- sscanf_s
- swscanf_s
- vsscanf_s
- vswscanf_s
- gets_s


#### 构建方法

- 编译步骤

1. 将src下的.c文件添加到构建脚本的源码清单中。

2. 在编译选项中指定头文件目录以及项目需要的编译选项（例如：在CFLAGS中添加 -Ipath_to_include -fstack-protector-strong -fPIC    -Wall -D_FORTIFY_SOURCE=2 -O2）。

3. 为每个.c文件编译生成.o文件 。

4. 根据项目需要将.o文件生成静态库或共享库使用。

- 编译示例：
```
gcc -o memcpy_s.o -c -Iinclude -fstack-protector-strong -fPIC -Wall -D_FORTIFY_SOURCE=2 -O2 src/memcpy_s.c
```
#### CMake构建方法
```
mkdir build && cd build
cmake ..
make
```
查看是否成功
```
[root@vbox build]# pwd
/root/securec-master/build
[root@vbox build]# ll
total 68
-rw-r--r--. 1 root root 12505 May 12 09:37 CMakeCache.txt
drwxr-xr-x. 6 root root  4096 May 12 09:37 CMakeFiles
-rw-r--r--. 1 root root  2078 May 12 09:37 cmake_install.cmake
drwxr-xr-x. 2 root root  4096 May 12 09:37 lib
-rw-r--r--. 1 root root 39094 May 12 09:37 Makefile
[root@vbox build]# ls -al lib/
total 464
drwxr-xr-x. 2 root root   4096 May 12 09:37 .
drwxr-xr-x. 4 root root   4096 May 12 09:37 ..
-rw-r--r--. 1 root root 464734 May 12 09:37 libsecurec.a
[root@vbox build]#

```

