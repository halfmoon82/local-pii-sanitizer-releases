# 第三方组件许可证声明（THIRD_PARTY_LICENSES）

本地脱敏 Agent（local-pii-sanitizer）为闭源商业软件，以编译后的原生应用（macOS `LocalPIISanitizer.app`）分发。
本表由 `scripts/gen_third_party_licenses.py` 按 `packaging/native/requirements.lock.txt`（Python 依赖）与
`packaging/native/vendor.lock`（随包外部二进制）自动生成：Python 包的许可证字段读自各包已安装的元数据
（License-Expression / License / Classifier），完整许可证文本随其 wheel 一起打进应用（`*.dist-info/`）；
非 Python 组件的许可证全文在应用内 `Contents/Resources/licenses/`（仓库 `packaging/native/licenses/`）。

## 1. Python 依赖（requirements.lock.txt）

| 包名 | 版本 | 许可证 |
|------|------|--------|
| annotated-doc | 0.0.5 | MIT |
| annotated-types | 0.8.0 | MIT |
| anyio | 4.14.2 | MIT |
| bottle | 0.13.4 | MIT |
| brotli | 1.2.0 | MIT |
| certifi | 2026.7.22 | MPL-2.0 |
| cffi | 2.1.1 | MIT-0 |
| click | 8.4.2 | BSD-3-Clause |
| cryptography | 48.0.1 | Apache-2.0 OR BSD-3-Clause |
| cssselect2 | 0.10.1 | BSD License |
| fastapi | 0.141.1 | MIT |
| firecrawl-anydoc | 0.1.9 | MIT |
| flatbuffers | 25.12.19 | Apache 2.0 |
| fonttools | 4.64.0 | MIT |
| h11 | 0.16.0 | MIT |
| httpcore | 1.0.9 | BSD-3-Clause |
| httptools | 0.8.0 | MIT |
| httpx | 0.28.1 | BSD-3-Clause |
| idna | 3.18 | BSD-3-Clause |
| iniconfig | 2.3.0 | MIT |
| numpy | 2.4.6 | BSD-3-Clause AND 0BSD AND MIT AND Zlib AND CC0-1.0 |
| ollama | 0.6.2 | MIT |
| onnxruntime | 1.28.0 | MIT License |
| opencv-python | 5.0.0.93 | Apache 2.0 |
| packaging | 26.3 | Apache-2.0 OR BSD-2-Clause |
| pillow | 12.3.0 | MIT-CMU |
| pluggy | 1.6.0 | MIT |
| protobuf | 7.35.1 | 3-Clause BSD License |
| proxy_tools | 0.1.0 | MIT |
| pyclipper | 1.4.0 | MIT |
| pycparser | 3.0 | BSD-3-Clause |
| pydantic | 2.13.4 | MIT |
| pydantic_core | 2.46.4 | MIT |
| pydyf | 0.12.1 | BSD License |
| Pygments | 2.20.0 | BSD-2-Clause |
| pyobjc-core | 12.2.2 | MIT |
| pyobjc-framework-Cocoa | 12.2.2 | MIT |
| pyobjc-framework-Quartz | 12.2.2 | MIT |
| pyobjc-framework-Security | 12.2.2 | MIT |
| pyobjc-framework-WebKit | 12.2.2 | MIT |
| pypdfium2 | 5.13.0 | BSD-3-Clause, Apache-2.0, dependency licenses |
| pyphen | 0.18.1 | GNU General Public License v2 or later (GPLv2+); GNU Lesser General Public License v2 or later (LGPLv2+); Mozilla Public License 1.1 (MPL 1.1) |
| pytest | 9.1.1 | MIT |
| python-dotenv | 1.2.3 | BSD-3-Clause |
| python-multipart | 0.0.32 | Apache-2.0 |
| pywebview | 5.4 | BSD 3-Clause License |
| PyYAML | 6.0.3 | MIT |
| rapidocr-onnxruntime | 1.4.4 | Apache-2.0 |
| shapely | 2.1.2 | BSD 3-Clause |
| six | 1.17.0 | MIT |
| starlette | 1.6.0 | BSD-3-Clause |
| tinycss2 | 1.5.1 | BSD License |
| tinyhtml5 | 2.1.0 | MIT License |
| tqdm | 4.70.0 | MPL-2.0 AND MIT |
| typing-inspection | 0.4.4 | MIT |
| typing_extensions | 4.16.0 | PSF-2.0 |
| uvicorn | 0.52.3 | BSD-3-Clause |
| uvloop | 0.22.1 | MIT License |
| watchfiles | 1.2.0 | MIT |
| weasyprint | 69.0 | BSD License |
| webencodings | 0.6.1 | BSD License |
| websockets | 17.0.1 | BSD-3-Clause |
| zopfli | 0.4.3 | Apache-2.0 |

## 2. pypdfium2 随带的 PDFium 二进制及其构建期依赖

pypdfium2（BSD-3-Clause / Apache-2.0；文档 CC-BY-4.0）的 wheel 内置预编译的 PDFium 库
（[pdfium-binaries](https://github.com/bblanchon/pdfium-binaries)）。PDFium 本身为 BSD-3-Clause，
其静态链接的构建期依赖各自许可证如下（清单来自 wheel 的 `METADATA` `License-File` 列表，
许可证全文在 `pypdfium2-*.dist-info/licenses/data/<平台>/BUILD_LICENSES/`）：

| 组件 | 许可证 | 全文文件 |
|------|--------|----------|
| pdfium | BSD-3-Clause | BUILD_LICENSES/pdfium.txt |
| pdfium-binaries | BSD-3-Clause | BUILD_LICENSES/pdfium-binaries.txt |
| abseil | Apache-2.0 | BUILD_LICENSES/abseil.txt |
| agg23 | AGG License（BSD 风格） | BUILD_LICENSES/agg23.txt |
| fast_float | Apache-2.0 / MIT / BSL-1.0 | BUILD_LICENSES/fast_float.txt |
| freetype | FTL（FreeType License） | BUILD_LICENSES/freetype.txt |
| icu | Unicode-3.0 / ICU | BUILD_LICENSES/icu.txt |
| lcms（Little-CMS） | MIT | BUILD_LICENSES/lcms.txt |
| libjpeg-turbo | IJG + BSD-3-Clause + Zlib | BUILD_LICENSES/libjpeg_turbo.ijg, libjpeg_turbo.md |
| libopenjpeg | BSD-2-Clause | BUILD_LICENSES/libopenjpeg.txt |
| libpng | PNG Reference Library License v2 | BUILD_LICENSES/libpng.txt |
| libtiff | libtiff License（MIT 风格） | BUILD_LICENSES/libtiff.txt |
| llvm-libc | Apache-2.0 WITH LLVM-exception | BUILD_LICENSES/llvm-libc.txt |
| simdutf | Apache-2.0 / MIT | BUILD_LICENSES/simdutf.txt |
| zlib | Zlib | BUILD_LICENSES/zlib.txt |

> 上表许可证名称为常见归类，以 wheel 内随附的全文文件为准；不同平台 wheel 的清单可能略有差异。

## 3. 随包分发的非 Python 组件

### 3.1 外部可执行文件（`Contents/Resources/bin/`，由本程序以子进程 / 本机 HTTP 方式调用）

| 组件 | 版本 | 许可证 | 调用方式 | 全文与来源 |
|------|------|--------|----------|------------|
| pandoc | 3.11 | GPL-2.0-or-later | 子进程调用（Markdown → docx/pdf），与本程序为独立程序（GPL "mere aggregation"） | `licenses/pandoc-COPYING.md`（GPL-2.0 全文）；源码 tarball、源码仓库与官方二进制地址见 `licenses/pandoc-SOURCE.txt`（<https://github.com/jgm/pandoc/archive/refs/tags/3.11.tar.gz>） |
| Ollama | v0.33.3 | MIT | 以私有端口拉起 `ollama serve` 子进程，经本机 HTTP 调用 | `licenses/ollama-LICENSE`；Ollama 官方发布件自带的第三方声明（llama.cpp、MLX、Go、xgrammar、cpp-httplib、dlpack、fmt、picojson）随 `Contents/Resources/bin/ollama-dist/*_LICENSE` 原样附带 |

pandoc 与 Ollama 的随包二进制均为官方发布件、未作任何修改，版本 / 下载地址 / sha256 钉死在 `packaging/native/vendor.lock`。
按 GPL 第 3 条，pandoc 对应版本的完整源码可从 `licenses/pandoc-SOURCE.txt` 所列地址获得；如需，本软件权利人亦可应要求提供该源码副本。

### 3.2 随包动态库（`Contents/Frameworks/`，WeasyPrint PDF 引擎与解释器运行时所需，动态链接、未修改）

| 组件 | 包内文件 | 许可证 | 核对依据 | 全文文件（`licenses/`） |
|------|----------|--------|----------|--------------------------|
| Pango（含 pangoft2） | libpango-1.0.0.dylib, libpangoft2-1.0.dylib | LGPL-2.0-or-later | Homebrew formula `pango`；上游 COPYING | pango-COPYING |
| GLib（含 GObject / GIO / GModule） | libglib-2.0.0.dylib, libgobject-2.0.0.dylib, libgio-2.0.0.dylib, libgmodule-2.0.0.dylib | LGPL-2.1-or-later | Homebrew formula `glib` | LGPL-2.1.txt |
| HarfBuzz（含 harfbuzz-subset） | libharfbuzz.0.dylib, libharfbuzz-subset.0.dylib | MIT（Old MIT） | Homebrew formula `harfbuzz`；上游 COPYING | harfbuzz-COPYING |
| Fontconfig | libfontconfig.1.dylib | HPND-sell-variant AND Unicode-3.0 AND MIT-Modern-Variant AND MIT（MIT 风格） | Homebrew formula `fontconfig`；上游 COPYING | fontconfig-COPYING |
| FreeType | libfreetype.6.dylib | FTL（FreeType License，二选一里取 FTL，不取 GPLv2） | Homebrew formula `freetype`；上游 LICENSE.TXT + docs/FTL.TXT | freetype-LICENSE.TXT, freetype-FTL.TXT |
| FriBidi | libfribidi.0.dylib | LGPL-2.1-or-later（库；GPL 仅覆盖其命令行工具，未随包） | Homebrew formula `fribidi`（GPL-2.0-or-later AND LGPL-2.1-or-later）；上游 COPYING 为 LGPL-2.1 | LGPL-2.1.txt |
| Graphite2 | libgraphite2.3.dylib | LGPL-2.1-or-later（四选一：MIT / MPL-2.0 / LGPL-2.1+ / GPL-2+） | Homebrew formula `graphite2`；上游 LICENSE | graphite2-LICENSE |
| GNU gettext 运行库 libintl | libintl.8.dylib | LGPL-2.1-or-later（运行库；GPL-3 仅覆盖 gettext 工具，未随包） | Homebrew formula `gettext`（GPL-3.0-or-later AND LGPL-2.1-or-later）；gettext-runtime/intl/COPYING.LIB | LGPL-2.1.txt |
| libthai | libthai.0.dylib | LGPL-2.1-or-later | Homebrew formula `libthai`；上游 COPYING | LGPL-2.1.txt |
| libdatrie | libdatrie.1.dylib | LGPL-2.1-or-later | Homebrew formula `libdatrie`；上游 COPYING | LGPL-2.1.txt |
| PCRE2 | libpcre2-8.0.dylib | BSD-3-Clause WITH PCRE2-exception | Homebrew formula `pcre2`；上游 LICENCE.md | pcre2-LICENCE.md |
| libpng | libpng16.16.dylib | libpng-2.0（PNG Reference Library License v2） | Homebrew formula `libpng`；上游 LICENSE | libpng-LICENSE |
| CPython 3.12 运行时 | libpython3.12.dylib（及标准库） | PSF-2.0（Python-2.0） | Homebrew formula `python@3.12`；上游 LICENSE.txt | python-LICENSE.txt |

- 上述动态库由构建机 Homebrew 安装、PyInstaller 收进应用，版本随构建时 Homebrew 当次安装版本（以 dmg 内文件为准）；
  全部为动态链接，本软件未修改其源码，用户可用同名同 ABI 的库文件替换（LGPL 第 6 条 / 第 4 条允许的方式）。
- FreeType 按 FTL 要求致谢：Portions of this software are copyright © The FreeType Project (www.freetype.org). All rights reserved.
- 其余随 Python wheel 一起打进应用的动态库（`cv2/.dylibs/`、`PIL/.dylibs/`、`shapely/.dylibs/`、`onnxruntime/capi/`、
  `pypdfium2_raw/`）属于对应 Python 包的发布件，许可证以各 wheel 的 `*.dist-info/licenses/`（如 opencv-python 的
  `LICENSE-3RD-PARTY.txt`）为准，本软件未增删其中任何文件。

## 4. 不随本软件分发、由用户自行获取的组件

| 组件 | 许可证 | 获取方式 | 用途 |
|------|--------|----------|------|
| Qwen 系列模型（config.yaml 指定） | Apache-2.0（以模型页为准，不同尺寸/版本可能采用 Qwen License） | 应用首次启动的「首次准备」页从 Ollama 官方模型库下载到本机数据目录（约 3.4GB，不随安装包分发） | 中文人名/公司名语义识别 |

## 5. 说明

- 本软件本体（编译后的 `src` 扩展模块、前端页面、配置、文档）为闭源商业软件，受 `LICENSE.txt`（最终用户许可协议）约束，不属于开源组件。
- 上述第三方组件的使用不改变其各自许可证赋予用户的权利；如发现遗漏或标注有误，请通过 LICENSE.txt 所列联系方式告知。
- 本文件为合规声明草稿，发布前需经法务审阅。
