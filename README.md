# FairyPlayer

一款面向本地媒体与在线流媒体的高性能播放器，提供 Windows 与 Linux 双版本，兼顾易用性与专业处理能力。

## 作者与官网

- 作者：RucLinux
- 官网：<https://www.myzhenai.com.cn>

## 技术栈

- PySide6 界面
- FFmpeg 工具链
- M3U8 支持
- NativeCore 加速（可选）

## 核心功能

### 1) 本地媒体播放

适用于日常视频、音乐、课程、录屏等文件的直接播放。

- 使用步骤：打开软件后，点击“打开文件”或直接拖拽媒体文件到窗口。
- 常用操作：拖动进度条快进/回退，调节音量，切换全屏，支持暂停与继续播放。
- 适用格式：常见 mp4、mkv、mp3、flac、wav 等主流格式（受系统编解码能力影响）。

建议：播放 4K 或高码率文件时，优先放在本地磁盘，避免网络盘造成卡顿。

### 2) 在线流媒体播放（M3U8）

适用于直播流、课程回放、网络点播地址等需要在线播放的场景。

- 使用步骤：在地址输入区域粘贴 M3U8 链接，点击“播放”即可开始加载。
- 网络要求：网络越稳定，首帧加载越快；弱网环境下可能出现缓冲。
- 故障排查：链接失效、跨域限制或源站限流时，可能无法播放。

建议：先在浏览器中确认链接有效，再粘贴到播放器中可减少排查时间。

### 3) 媒体信息探测

用于查看视频/音频的关键参数，便于转码前评估。

- 可查看信息：时长、分辨率、编码格式、码率、音轨等。
- 使用方式：加载媒体后打开“属性/信息”面板查看详情。
- 典型用途：判断素材是否需要转码、封装或统一参数。

### 4) 视频截图

用于截取当前播放画面，生成图片文件用于预览或记录。

- 使用步骤：播放到目标时间点，点击“截图”按钮。
- 输出结果：自动生成 PNG 图片，保存到默认输出目录。
- 适用场景：制作封面、教学截图、问题反馈定位。

### 5) 转码与封装

用于将不兼容素材转换为通用格式，或仅更换容器以提升兼容性。

- 转码：可将源视频转为更通用的 H.264 + AAC 组合。
- 封装：在不重编码前提下更换封装容器，速度更快。
- 使用建议：先用“媒体信息探测”确认源文件参数，再选择转码或封装。

建议：批量处理前先用 1 个样例文件验证输出效果与兼容性。

## Windows / Linux 使用说明

- Windows：解压后双击主程序 `FairyPlayer.exe` 启动。
- Linux：进入目录后执行 `./run.sh`（首次可先执行 `chmod +x run.sh FairyPlayer`）。
- 若启动异常，请确认发布目录内文件完整，且不要随意移动核心文件。

## 目录结构说明

### Windows 目录示例

- `FairyPlayer.exe`：主程序入口，双击即可启动。
- `bin/`：程序运行依赖的可执行组件目录，请勿删除或改名。
- `dlls/`：动态链接库目录，提供图形、多媒体等底层运行支持。
- `images/`（或 `img/`）：界面图标与图片资源目录。
- `logs/`：运行日志目录（若存在），用于问题排查。

建议：Windows 下将整个目录放在同一路径，避免只复制 exe 导致缺失组件。

### Linux 目录示例

- `FairyPlayer`：Linux 主可执行文件。
- `run.sh`：推荐启动脚本，会自动处理运行环境后启动主程序。
- `code/`：运行模块与动态库目录（如 `native_core`、FFmpeg 相关文件）。
- `images/`（或 `img/`）：界面图标与图片资源目录。
- `logs/`：运行日志目录（若存在），用于故障定位。

建议：Linux 下优先执行 `./run.sh`，并确保 `FairyPlayer` 与 `run.sh` 有执行权限。

## 发布说明

- 本软件采用独立目录发布，非单文件打包（Windows / Linux 均如此）。
- Windows：请保持 `FairyPlayer.exe`、`bin/`、`dlls/` 与资源目录完整。
- Linux：`code/` 中的原生模块与 FFmpeg 相关文件为运行必需组件。
- 通用资源：图标与界面资源位于 `images/`（或 `img/`）目录，请勿删除。

<img width="1356" height="870" alt="linux-2" src="https://github.com/user-attachments/assets/8a113a50-44ce-45eb-a32f-097e4305ba42" />

<img width="1358" height="868" alt="linux-1" src="https://github.com/user-attachments/assets/bad5a727-ed05-44cb-a29f-6cc079e75d3c" />

<img width="1353" height="868" alt="linux-3" src="https://github.com/user-attachments/assets/2f08bad5-4ae3-4746-b0c5-f8765cb5dd25" />


## 下载与安装

请选择任意网盘下载，进入网盘后打开 **FairyPlayer** 目录即可获取对应版本安装包。

- 百度网盘：<https://pan.baidu.com/s/1cu9RomarbHZmaxm5fYaKFg?pwd=79uu>  
  提取码：`79uu`

- 夸克网盘：<https://pan.quark.cn/s/68226354d0df?pwd=WqYX>  
  提取码：`WqYX`

- 天翼网盘：<https://cloud.189.cn/t/zUbmE3EVJjUj>  
  提取码：`zw01`

---

FairyPlayer © 2026 · Author: RucLinux · Website: <https://www.myzhenai.com.cn>

