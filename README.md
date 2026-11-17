# chat2data-tech

本目录存放 **chat2ExcelEasy** 和 **chat2Data** 两个项目的源代码。

---

## 目录结构

```
|-- chat2data-tech          # 该目录下存放 chat2ExcelEasy 和 chat2Data 项目源代码
| |-- LICENSE
| |-- README.en.md
| |-- README.md
| |-- chat2ExcelEasy       # 该目录下存放 chat2ExcelEasy 的所有文件
| | |-- build
| | | `-- www              # 存放前端代码
| | |-- docment            # 存放所有提示词
| | |-- source             # 存放项目代码
| | `-- test               # 存放测试代码
| `-- svc_chat2Data        # 该目录下存放 svc_chat2Data 项目所有文件
`-- libSource              # 该目录下存放 ChatSDK、OpenXLSX、C++脚手架源码
```

> 注：`libSource` 与 `chat2data-tech` 同级，位于工作目录 `/home/dev/workspace` 下。

---

## 各目录职责说明

| 目录 | 职责说明 |
|---|---|
| `chat2data-tech/` | chat2ExcelEasy 和 chat2Data 两个项目源代码的根目录 |
| `chat2data-tech/chat2ExcelEasy/` | chat2ExcelEasy 项目的全部文件 |
| `chat2data-tech/chat2ExcelEasy/build/` | 构建产物目录 |
| `chat2data-tech/chat2ExcelEasy/build/www/` | **前端代码**存放处 |
| `chat2data-tech/chat2ExcelEasy/docment/` | **所有提示词**存放处 |
| `chat2data-tech/chat2ExcelEasy/source/` | **项目代码**存放处 |
| `chat2data-tech/chat2ExcelEasy/test/` | **测试代码**存放处 |
| `chat2data-tech/svc_chat2Data/` | svc_chat2Data 项目的全部文件（服务端） |
| `libSource/` | 第三方源码：ChatSDK、OpenXLSX、C++ 脚手架 |

### 顶层文件

| 文件 | 说明 |
|---|---|
| `LICENSE` | 许可证（**待补**） |
| `README.md` | 本文件 |
| `README.en.md` | 英文版说明（**待补**） |
| `.gitignore` | 忽略规则：编译产物 / IDE / 依赖 / 敏感文件 / 日志 |

---

## libSource：第三方源码

`libSource/` 存放三个第三方项目源码，均由 `/home/dev/openPrjSource` 复制而来（保留完整 git 历史，属主为 `dev`，可直接编辑）：

| 目录 | 来源项目 | 说明 |
|---|---|---|
| `libSource/ChatSDK/` | `AIModelAcessTech` | 多模型大模型接入 SDK + HTTP 聊天服务器。含 `sdk/`（静态库 `libai_chat_sdk.a`）、`ChatServer/`、`test/`、`板书/` |
| `libSource/OpenXLSX/` | `OpenXLSX` | Excel(.xlsx) 读写库，BSD 3-Clause，零外部依赖 |
| `libSource/scaffold/` | `cpp-microservice-scaffold` | C++ 微服务组件脚手架，编译产物 `libbite_scaffold.a` + 21 个示例 |

---

## ⚠️ 注意事项

1. **`.gitignore` 的 `build/` 会连带忽略前端代码**
   当前 `.gitignore` 含 `build/` 规则，会把 `chat2ExcelEasy/build/www/`（前端代码）排除在版本控制之外。若前端代码需要入库，改为精确忽略：

   ```gitignore
   build/*
   !build/www/
   ```

2. **`docment` 是既有拼写**（非 `document`），目录名保持不变，避免与已建路径不匹配。

3. **`svc_chat2Data` 与 `chat2ExcelEasy` 为并列关系**：前者存放服务端项目代码，后者存放客户端/前端项目代码。

---

## 相关文档

- `../使用说明.md` —— `libSource` 三个第三方项目的编译、运行、API 说明与已知问题（已实测验证）
