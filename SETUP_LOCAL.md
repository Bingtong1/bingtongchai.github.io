# Windows 本地 Jekyll 环境配置指南

## 第一步：安装 Ruby

### 方法1：使用 RubyInstaller（推荐）

1. **下载 RubyInstaller**
   - 访问：https://rubyinstaller.org/downloads/
   - 下载 **Ruby+Devkit 3.2.x** 版本（推荐 3.2.6 或最新版）
   - 选择 x64 版本（如果你的系统是64位）

2. **安装 Ruby**
   - 运行下载的 `.exe` 安装程序
   - **重要**：安装时务必勾选 "Add Ruby executables to your PATH"
   - 选择安装路径（默认即可）
   - 点击安装

3. **安装开发工具（Devkit）**
   - 安装完成后，会自动打开一个命令行窗口
   - 如果没有自动打开，打开新的 PowerShell 或命令提示符
   - 运行以下命令：
     ```
     ridk install
     ```
   - 选择选项 **3**（安装所有组件：MSYS2 base installation 和 MINGW development toolchain）

4. **验证安装**
   - 重新打开一个新的 PowerShell 窗口（重要：必须重新打开）
   - 运行：
     ```powershell
     ruby --version
     ```
   - 应该显示类似：`ruby 3.2.x`

## 第二步：安装 Bundler

在 PowerShell 中运行：

```powershell
gem install bundler
```

## 第三步：安装项目依赖

进入项目目录：

```powershell
cd C:\Users\22170\Desktop\Github.io\bingtongchai.github.io
bundle install
```

如果遇到权限错误，可以使用：

```powershell
bundle config set --local path 'vendor/bundle'
bundle install
```

## 第四步：运行本地服务器

```powershell
bundle exec jekyll serve -l -H localhost
```

或者：

```powershell
jekyll serve -l -H localhost
```

服务器启动后，访问：http://localhost:4000

## 常见问题解决

### 问题1：`bundle` 或 `jekyll` 命令未找到
- 确保 Ruby 安装时勾选了 "Add Ruby executables to your PATH"
- 重新打开 PowerShell 窗口（环境变量需要重新加载）

### 问题2：权限错误
```powershell
bundle config set --local path 'vendor/bundle'
bundle install
```

### 问题3：需要安装 Node.js
Jekyll 需要 Node.js 来运行某些功能：
- 下载：https://nodejs.org/
- 安装 LTS 版本
- 重新打开 PowerShell

### 问题4：SSL 证书错误
```powershell
gem sources --remove https://rubygems.org/
gem sources --add https://rubygems.org/ --trust
```

## 使用方法

### 启动服务器
```powershell
bundle exec jekyll serve -l -H localhost
```

### 停止服务器
在运行服务器的终端窗口按 `Ctrl + C`

### 查看更改
- Markdown 文件（.md）和 HTML 文件的更改会自动刷新
- 配置文件（_config.yml）的更改需要停止并重启服务器

## 快速命令参考

```powershell
# 进入项目目录
cd C:\Users\22170\Desktop\Github.io\bingtongchai.github.io

# 安装依赖（首次运行）
bundle install

# 启动服务器
bundle exec jekyll serve -l -H localhost

# 或者简单方式
jekyll serve -l -H localhost
```


