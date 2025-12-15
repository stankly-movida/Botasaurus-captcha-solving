# 🤖 Botasaurus 验证码解决集成方案

[![Python Version](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Stars](https://img.shields.io/github/stars/omkarcloud/botasaurus?style=social)](https://github.com/omkarcloud/botasaurus)

一个强大且开箱即用的 Python 模板，用于在网络爬虫项目中，结合 **Botasaurus**（反检测）和 **CapSolver**（验证码解决），自动绕过 reCAPTCHA v2、reCAPTCHA v3 和 Cloudflare Turnstile。

---

## ✨ 主要特性

- **无缝集成:** 结合了 Botasaurus 的反检测能力和 CapSolver 的 API 优势。
- **多验证码支持:** 提供了 reCAPTCHA v2、v3 和 Cloudflare Turnstile 的完整示例。
- **清晰架构:** 配置、辅助函数和示例代码分离，易于维护和扩展。
- **令牌注入:** 演示了如何使用 Botasaurus 将已解决的验证码令牌正确注入到浏览器上下文中。

## 🚀 快速开始

### 1. 前置条件

- Python 3.8+
- 一个 CapSolver API 密钥（可从 [CapSolver 控制台](https://dashboard.capsolver.com/dashboard/overview/?utm_source=github&utm_medium=readme&utm_campaign=manus-rewrite-botasaurus) 获取）

### 2. 安装

克隆仓库并安装依赖：

```bash
git clone https://github.com/your-username/this-repo.git
cd this-repo
pip install -r requirements.txt
```

### 3. 配置

在项目根目录创建 `.env` 文件并添加您的 API 密钥：

```env
# .env
CAPSOLVER_API_KEY=CAP-YOUR_API_KEY_HERE
```

### 4. 运行示例

执行 `examples/` 目录下的任一示例脚本：

```bash
# reCAPTCHA v2 示例
python examples/recaptcha_v2.py

# Cloudflare Turnstile 示例
python examples/turnstile.py
```

---

## 📂 项目结构

```
.
├── README.md
├── README_zh.md (中文说明)
├── LICENSE
├── CONTRIBUTING.md
├── requirements.txt
├── .env (已忽略)
└── src/
    ├── config.py             # 加载 API 密钥和定义 API 端点
    └── capsolver_helper.py   # 用于创建和轮询 CapSolver 任务的核心函数
└── examples/
    ├── recaptcha_v2.py       # reCAPTCHA v2 完整示例
    ├── recaptcha_v3.py       # reCAPTCHA v3 完整示例
    └── turnstile.py          # Cloudflare Turnstile 完整示例
```

---

## ⚙️ 核心实现

核心逻辑分为配置模块和解决辅助函数。

### `src/config.py`

处理环境变量加载和 API 端点定义。

```python
# src/config.py
# ... (代码内容与英文版相同) ...
```

### `src/capsolver_helper.py`

包含用于解决不同验证码类型的可重用函数。

```python
# src/capsolver_helper.py (README 简化版)
# ... (代码内容与英文版相同) ...
```

---

## 💡 最佳实践

| 实践 | 描述 |
| :--- | :--- |
| **即时使用** | 验证码令牌有效期极短（约 2 分钟）。在收到令牌后，必须立即注入并提交。 |
| **错误处理** | 始终使用 `try...except` 块来处理 API 调用失败，确保程序健壮性。 |
| **速率限制** | 在操作之间使用 `driver.sleep()` 增加延迟，模拟人类行为，避免触发反爬机制。 |
| **配置验证** | 在进行任何 API 调用之前，使用 `Config.validate()` 方法检查 API 密钥是否配置正确。 |

---

## 🎁 特别优惠

立即提升您的自动化预算！充值 CapSolver 账户时使用奖励代码 **CAPN**，即可在每次充值时额外获得 **5% 的奖励金**——无上限！

立即在您的 [CapSolver 控制台](https://dashboard.capsolver.com/dashboard/overview/?utm_source=github&utm_medium=readme&utm_campaign=manus-rewrite-botasaurus) 兑换吧！

![](https://assets.capsolver.com/prod/posts/aws-waf-captcha-solution/qMMCl6UIh7Ob-d2b5ca33bd970f64a6301fa75ae2eb22.png)

---

## 🤝 贡献

我们欢迎社区贡献！请参阅 [CONTRIBUTING.md](CONTRIBUTING.md) 了解如何提交拉取请求、报告错误和建议功能。

## 📄 许可证

本项目采用 MIT 许可证 - 详情请参阅 [LICENSE](LICENSE) 文件。

## 🔗 资源链接

- [Botasaurus GitHub 仓库](https://github.com/omkarcloud/botasaurus)
- [CapSolver 控制台](https://dashboard.capsolver.com/dashboard/overview/?utm_source=github&utm_medium=readme&utm_campaign=manus-rewrite-botasaurus)
- [CapSolver 验证码检测扩展](https://chromewebstore.google.com/detail/capsolver-captcha-solver)
- [识别验证码参数指南](https://www.capsolver.com/blog/Extension/identify-any-captcha-and-parameters)
