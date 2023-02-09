#.Net6基础镜像--默认下载这个镜像
FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
#设置容器工作目录
WORKDIR /app 
#这里是将镜像的目录下的文件拷贝到 容器的 /app 目录下面
COPY . /app
#默认启动端口号是80
EXPOSE 80/tcp 
# 运行 CMD命令, 注意第二个字符串要换成你当前项目的dll名称
ENTRYPOINT ["dotnet", "net-template.Api.dll"]