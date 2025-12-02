# 本地运行 Jekyll 网站指南

## 安装 Ruby（Windows）

1. 下载 Ruby+Devkit：
   - 访问：https://rubyinstaller.org/downloads/
   - 下载 Ruby+Devkit 3.2.x（推荐版本）
   - 运行安装程序，**务必勾选"Add Ruby executables to your PATH"**

2. 安装完成后，在安装程序的最后一步选择运行 `ridk install`，选择选项 3（安装所有组件）

3. 重启 PowerShell 或命令提示符

## 安装依赖

打开 PowerShell，进入项目目录，运行：

```powershell
cd C:\Users\22170\Desktop\Github.io\bingtongchai.github.io
gem install bundler
bundle install
```

## 运行本地服务器

```powershell
bundle exec jekyll serve -l -H localhost
```

然后在浏览器中访问：http://localhost:4000

## 注意事项

- 如果修改了 `_config.yml`，需要停止服务器（Ctrl+C）并重新启动
- Markdown 文件的更改会自动刷新，无需重启


