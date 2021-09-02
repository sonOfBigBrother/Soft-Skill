# 无法加载文件 ***.ps1，因为在此系统上禁止运行脚本 

1. 以**管理员身份**运行powershell；

2. 输入以下命令后输入`Y`回车后即可：

   ```powershell
   set-ExecutionPolicy RemoteSigned
   ```

3. 再次重新执行命令。