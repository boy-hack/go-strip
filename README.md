# go-strip
Go编译会自带一堆信息，通过这些信息基本可以还原Go的源码架构,甚至可以用作溯源。本工具可以直接从go编译好的二进制中消除这些信息。

- 支持Go编译的 Windows、Mac、Linux程序
- 支持AMD64,386架构
- Go1.13和Go1.16用于解析的数据结构不太一样，但这款工具都支持

支持消除/混淆
- 函数名称
- 函数路径
- Go Struct
- Type
- Go Compiler Version
- Go BuildID
- Go Root Path

## Useage
go编译出二进制，
```
go build -ldflags "-s -w" .
```
之后即可使用工具进行混淆消除
```
                       _        _
                      | |      (_)
  __ _  ___ ______ ___| |_ _ __ _ _ __
 / _  |/ _ \______/ __| __| '__| | '_ \
| (_| | (_) |     \__ \ |_| |  | | |_) |
\__, |\___/      |___/\__|_|  |_| .__/
__/ |                          | |
|___/                           |_|

Usage of go-strip:
  -a    是否消除Go的编译信息
  -f string
        源文件名
  -output string
        另保存的文件名
```
执行
```
go-strip -f binary.exe
```
将会打印出读取的信息

执行
```
go-strip -f binary.exe -a -output new.exe
```
new.exe即是混淆后的二进制文件
## Paper
- https://mp.weixin.qq.com/s?__biz=MzU2NzcwNTY3Mg==&mid=2247484130&idx=1&sn=d482026bcd9d74b4b5bb5a62f02af10e&chksm=fc986bc5cbefe2d3e74ac3e892c10e9c65f968ac32bfbd3b0f373e09fe65c39f58ea3e62107f&token=1662333611&lang=zh_CN#rd

## 代码
代码已开源，关注公众号 "Hacking就是好玩" 回复 知识星球 即可获取
