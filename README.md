# solutions

这是目前可能的方法：

> 1. 增加 privileged 特权运行配置
> 2. hostNetwork 配置为 default
> 3. nodeserver.go 中 umount使用 -l -f 参数

详细说明：

1. 文件目录名中带有 host 说明 配置了 hostNetwork

2. 文件目录名中带有 host-default 说明将hostNetwork的配置改为了default

3. 文件目录名中带有 nohost 说明 取消了 hostNetwork

4. 文件目录名中带有 privilege 说明进行了privileged配置

5. nodeserver.go 中 mount 之后增加 isMounted检查，判断是否挂载成功

6. nodeserver.go 中 umount 失败后尝试 -l -f 参数

   



