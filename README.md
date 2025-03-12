# VSCode Proto Reference Extension

这是一个 VSCode 扩展，用于在 Go 代码中快速定位和跳转到对应的 Proto 定义。通过 CodeLens 功能，您可以在 Go 代码中直接看到并跳转到相关的 Proto 消息定义或 RPC 方法定义。

## 功能特性

- 🔍 自动检测 Go 代码中的 Proto 生成的结构体和方法
- 👆 提供直观的 CodeLens 界面，显示 "Find Proto Definition" 链接
- 🚀 一键跳转到对应的 Proto 文件定义处
- 🔄 支持递归搜索整个工作区的 Proto 文件
- ⚡ 实时响应，无需额外配置

## 安装

### 从 VSCode Marketplace 安装

1. 打开 VSCode
2. 按下 `Ctrl+P` (Windows/Linux) 或 `Cmd+P` (Mac)
3. 输入 `ext install vscode-proto-extension`
4. 按回车安装

### 从源码安装

1. 克隆仓库：
```bash
git clone https://github.com/yourusername/vscode-proto-extension.git
cd vscode-proto-extension
```

2. 安装依赖：
```bash
npm install
```

3. 编译：
```bash
npm run compile
```

4. 在 VSCode 中按 F5 运行调试版本

## 使用方法

1. 打开包含 Proto 生成的 Go 代码的文件
2. 在结构体或方法定义上方，您会看到 "Find Proto Definition" 的 CodeLens
3. 点击 CodeLens 链接，扩展会自动搜索并跳转到对应的 Proto 定义处

### 示例

```go
// 在 Go 代码中
type User struct {
    // ...
}

// 点击 "Find Proto Definition" 会跳转到
// proto/user.proto
message User {
    // ...
}
```

## 支持的 Go 代码模式

该扩展支持以下 Go 代码模式：

- Proto 生成的结构体定义：
```go
type MessageName struct {
    // ...
}
```

- Proto 生成的 RPC 方法：
```go
func (s *ServiceName) MethodName(ctx context.Context, req *Request) (*Response, error) {
    // ...
}
```

## 配置

目前扩展无需额外配置即可使用。它会自动：

- 在工作区中搜索所有 `.proto` 文件
- 匹配 Go 代码中的 Proto 相关定义
- 提供 CodeLens 跳转功能

## 开发

### 构建

```bash
npm install
npm run compile
```

### 调试

1. 在 VSCode 中打开项目
2. 按 F5 启动调试
3. 在新打开的 VSCode 窗口中测试扩展

## 贡献

欢迎提交 Issue 和 Pull Request！

## 许可证

MIT License 