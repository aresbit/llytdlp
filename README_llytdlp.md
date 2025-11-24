# llytdlp - AI驱动的yt-dlp命令生成器

`llytdlp` 是一个智能命令行工具，通过AI大模型将自然语言描述转换为yt-dlp命令，让你无需记忆复杂的yt-dlp语法即可完成视频下载任务。

## ✨ 功能特性

- **自然语言转yt-dlp命令**：用中文或英文描述需求，自动生成对应命令
- **多AI模型支持**：支持DeepSeek和Kimi(Moonshot AI)两种大模型
- **智能文件名**：自动为下载文件生成有意义的名称
- **多功能支持**：支持视频下载、音频提取、播放列表、字幕等
- **安全默认配置**：自动添加错误忽略和不覆盖等安全选项
- **执行确认**：显示生成的命令，确认后才执行，避免误操作

## 🚀 安装方法

1. 克隆仓库：
   ```bash
   git clone https://github.com/aresbit/llmpeg.git
   cd llmpeg
   ```

2. 赋予执行权限：
   ```bash
   chmod +x llytdlp
   ```

3. 将文件移动到系统PATH：
   ```bash
   sudo mv llytdlp /usr/local/bin/
   ```

## 🔑 API密钥配置

### 使用DeepSeek（推荐）
```bash
export DEEPSEEK_API_KEY="你的DeepSeek API密钥"
```

### 使用Kimi(Moonshot AI)
```bash
export KIMI_API_KEY="你的Moonshot AI API密钥"
```

**建议**：将上述命令添加到 `~/.bashrc` 或 `~/.zshrc` 中，使其永久生效。

## 📖 使用示例

### 基础用法
```bash
# 下载单个视频
llytdlp "下载这个YouTube视频 https://www.youtube.com/watch?v=dQw4w9WgXcQ"

# 下载B站视频
llytdlp "下载这个B站视频 https://www.bilibili.com/video/BV1xxxxxxx"

# 提取音频
llytdlp "从YouTube视频提取音频 https://www.youtube.com/watch?v=dQw4w9WgXcQ"

# 下载播放列表
llytdlp "下载这个播放列表 https://www.youtube.com/playlist?list=PLxxxxxxx"
```

### 高级用法
```bash
# 下载带字幕的视频
llytdlp "下载带中文字幕的YouTube视频 https://www.youtube.com/watch?v=dQw4w9WgXcQ"

# 下载为MP3并指定质量
llytdlp "下载YouTube视频为320k MP3 https://www.youtube.com/watch?v=dQw4w9WgXcQ"

# 下载最佳质量视频
llytdlp "下载最佳质量的YouTube视频 https://www.youtube.com/watch?v=dQw4w9WgXcQ"

# 下载特定格式
llytdlp "下载YouTube视频为MP4格式 https://www.youtube.com/watch?v=dQw4w9WgXcQ"

# 下载并保存缩略图
llytdlp "下载YouTube视频并保存缩略图 https://www.youtube.com/watch?v=dQw4w9WgXcQ"
```

### 中文描述示例
```bash
# 下载YouTube视频
llytdlp "下载这个YouTube视频 https://www.youtube.com/watch?v=dQw4w9WgXcQ"

# 提取音频
llytdlp "把这个视频的音乐提取出来 https://music.youtube.com/watch?v=xxxx"

# 下载播放列表
llytdlp "下载整个播放列表 https://www.youtube.com/watch?v=xxx&list=PLxxxx"

# 下载带字幕
llytdlp "下载这个带字幕的视频 https://www.youtube.com/watch?v=xxxx"

# 限制下载速度
llytdlp "用1M速度下载这个视频 https://www.youtube.com/watch?v=xxxx"
```

### 英文描述示例
```bash
# Download YouTube video
llytdlp "download this YouTube video https://www.youtube.com/watch?v=xxxx"

# Extract audio
llytdlp "extract audio from this YouTube video https://www.youtube.com/watch?v=xxxx"

# Download playlist
llytdlp "download this entire playlist https://www.youtube.com/playlist?list=xxxx"

# Download with subtitles
llytdlp "download YouTube video with English subtitles https://www.youtube.com/watch?v=xxxx"

# Download specific format
llytdlp "download YouTube video as MP4 https://www.youtube.com/watch?v=xxxx"
```

## 🎯 支持的操作类型

- **视频下载**：支持YouTube、B站、Twitter等数千个网站
- **音频提取**：从视频中提取音频，支持多种格式
- **播放列表下载**：自动识别并下载整个播放列表
- **字幕下载**：下载并嵌入字幕，支持多语言
- **缩略图下载**：保存视频缩略图
- **格式转换**：自动转换到指定格式
- **质量选择**：自动选择最佳质量或用户指定质量
- **速度限制**：支持下载速度限制功能

## ⚠️ 注意事项

1. **使用前请确认**：工具会显示生成的yt-dlp命令，按Enter执行，Ctrl+C取消
2. **合规下载**：仅下载您有权利下载的内容，尊重版权
3. **大文件处理**：大文件下载可能需要较长时间，请耐心等待
4. **网络连接**：确保网络连接稳定，下载过程中可重复调用
5. **API配额**：注意您的API密钥使用额度，避免超额使用

## 🔧 依赖要求

- **yt-dlp**：必须预先安装yt-dlp
  - macOS: `brew install yt-dlp`
  - Ubuntu/Debian: `sudo apt install yt-dlp`
  - 其他系统：[官方安装指南](https://github.com/yt-dlp/yt-dlp#installation)

- **curl**：用于API调用（通常系统已预装）

- **FFmpeg**（可选）：用于音视频处理

## 🛠️ 故障排除

### 常见问题

1. **"No API key found"错误**
   - 确保已设置 `DEEPSEEK_API_KEY` 或 `KIMI_API_KEY`
   - 运行 `echo $DEEPSEEK_API_KEY` 检查环境变量

2. **"yt-dlp: command not found"错误**
   - 确认yt-dlp已安装：`yt-dlp --version`
   - 参考安装方法重新安装

3. **下载失败或格式不支持**
   - 检查视频链接是否有效
   - 尝试不同的描述方式或手动指定格式

4. **API调用失败**
   - 检查网络连接
   - 确认API密钥有效且有足够余额

5. **视频无法解析**
   - 某些网站可能需要更新yt-dlp版本
   - 运行 `yt-dlp -U` 更新到最新版本

## 🤝 贡献指南

欢迎提交Issue和Pull Request！如果你发现了问题或有改进建议，请通过以下方式参与：

1. Fork本项目
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 创建Pull Request

## 📄 许可证

本项目采用MIT许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。

## 🌟 致谢

- 感谢DeepSeek和Moonshot AI提供强大的AI模型
- 感谢yt-dlp团队和开源社区提供的优秀视频下载工具