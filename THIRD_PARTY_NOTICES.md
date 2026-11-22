# 第三方组件

Media Info 随应用内置以下开源命令行工具及其运行库。应用以独立子进程调用这些工具，并在 App Sandbox 中运行。各组件保留自己的许可证；Media Info 的界面由作者独立实现，没有复制第三方应用的界面代码。

完整的许可文本、版权声明、构建信息和逐文件 SHA-256 清单随应用附带，位于：

```
Media Info.app/Contents/Resources/Licenses/
```

其中 `NOTICE.txt` 是总览，`Engines/SOURCES.txt` 与 `Additional/SOURCES.txt` 列出全部依赖的源码地址。

## 主要工具

| 组件 | 版本 | 许可证 | 源码 |
| --- | --- | --- | --- |
| FFmpeg / FFprobe | 9.0.1（LGPL 构建，修订 1） | LGPL-2.1-or-later | [预编译发布及对应源码](https://github.com/dfloresc/ffmpeg-macos-builds/releases/tag/v9.0.1-1) · [FFmpeg](https://ffmpeg.org/) |
| ExifTool | 13.59 | 与 Perl 相同（Artistic / GPL） | [固定提交](https://github.com/exiftool/exiftool/tree/2200871d9cef988051d2a99d67df3bda6cbb30a8) |
| Exiv2 | 0.28.8 | GPL-2.0-or-later | [v0.28.8](https://github.com/Exiv2/exiv2/tree/v0.28.8) |
| Bento4 mp4dump | 1.6.0-641 | GPL-2.0 | [源码包](https://www.bok.net/Bento4/source/Bento4-SRC-1-6-0-641.zip) |
| MediaInfo CLI | 26.01 | BSD-2-Clause | [源码包](https://mediaarea.net/download/binary/mediainfo/26.01/MediaInfo_CLI_26.01_GNU_FromSource.tar.xz) |
| GPAC MP4Box | 26.02.0 | LGPL-2.1-or-later | [v26.02.0](https://github.com/gpac/gpac/archive/refs/tags/v26.02.0.tar.gz) |
| MKVToolNix | 97.0 | GPL-2.0-or-later | [源码包](https://mkvtoolnix.download/sources/mkvtoolnix-97.0.tar.xz) |
| GStreamer | 1.28.1 | LGPL-2.0-or-later、LGPL-2.1-or-later、MIT | [源码包](https://gitlab.freedesktop.org/gstreamer/gstreamer/-/archive/1.28.1/gstreamer-1.28.1.tar.bz2) |
| LibRaw raw-identify | 0.22.0 | LGPL-2.1-only 或 CDDL-1.0 | [源码包](https://www.libraw.org/data/LibRaw-0.22.0.tar.gz) |
| libheif heif-info | 1.21.2 | LGPL-3.0-only | [源码包](https://github.com/strukturag/libheif/releases/download/v1.21.2/libheif-1.21.2.tar.gz) |
| libsndfile sndfile-info | 1.2.2 | LGPL-2.1-or-later | [源码包](https://github.com/libsndfile/libsndfile/releases/download/1.2.2/libsndfile-1.2.2.tar.xz) |

## 运行库与说明

- **Exiv2 的运行库**：Brotli 1.2.0（MIT）、gettext 1.0 的 libintl（LGPL-2.1-or-later）、inih r62（BSD-3-Clause）。
- **MediaInfo、GPAC、MKVToolNix、GStreamer、LibRaw、libheif、libsndfile** 及其依赖来自固定版本的 Homebrew 预编译包（[homebrew-core 快照 3386f39](https://github.com/Homebrew/homebrew-core/tree/3386f39024b572971268729712596a0ec154291d)）。这些依赖中包含 Homebrew 构建的 FFmpeg 8.0.1 运行库（GPL-2.0-or-later，含 x264、x265），与上表的 FFmpeg / FFprobe 9.0.1 LGPL 版本相互独立。
- 为了随应用内置，部分预编译文件的 Mach-O 依赖路径改成了应用内部的相对路径；没有修改或重新编译上游源码。
- 如需取得任一 GPL / LGPL 组件的对应源码而上述链接失效，请通过 [Issues](https://github.com/Andyshenjx/Media-Info-Mac/issues) 联系作者。

本软件基于部分 Independent JPEG Group 的工作（经由 FFmpeg 的 JPEG 相关代码）。
