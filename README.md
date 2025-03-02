# 🍼 Baby Naptime

> *Find vulnerabilities while the baby sleeps!*

An open source implementation inspired by Google's Project Naptime - a powerful vulnerability analysis tool that uses Large Language Models (LLMs) to discover and exploit native vulnerabilities.

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
![Python 3.7+](https://img.shields.io/badge/python-3.7+-blue.svg)
![Open Source](https://img.shields.io/badge/Open%20Source-%E2%9D%A4-red)

## 🔍 Overview

Baby Naptime leverages the intelligence of LLMs to revolutionize security analysis:

- **Smart vulnerability detection** that understands code context
- **Automated exploit generation** to prove concepts
- **Memory corruption analysis** that catches what static analyzers miss
- **Integrated debugging** with security-focused insights

## ✨ Features

| Feature | Description |
|---------|-------------|
| 🧠 **Intelligent Analysis** | Uses LLMs to understand code semantics and identify potential vulnerabilities |
| 🛠️ **Automated Exploitation** | Generates and tests exploit payloads with minimal user intervention |
| 💾 **Memory Analysis** | Deep inspection of memory layouts and corruption patterns |
| 🔬 **Advanced Debugging** | GDB integration with security-focused analysis capabilities |
| 🧭 **Code Navigation** | Smart traversal of codebases to focus on vulnerability-prone areas |
| 📝 **Reporting** | Detailed vulnerability reports with exploitation paths and remediation suggestions |

## 📋 Requirements

- Python 3.7 or higher
- GDB debugger
- C/C++ compiler (g++)
- OpenAI API key
- Required Python packages (see `requirements.txt`)

## 🚀 Quick Start

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/baby-naptime.git
cd baby-naptime

# Install dependencies
pip install -r requirements.txt

# Set up your OpenAI API key
export OPENAI_API_KEY='your-api-key-here'
```

### Usage

Basic command:

```bash
python run.py -c <code_file> [options]
```

#### Command Options

```
-c, --code_file        Path to the source code file to analyze (required)
-d, --code-directory   Directory containing additional source files (default: ".")
-m, --max-iterations   Maximum number of analysis iterations (default: 100)
-l, --llm-model        LLM model to use (choices: gpt-3.5-turbo, gpt-4o, gpt-4o-mini, o3-mini, o1-preview)
-f, --main-function    Entry function to begin analysis (default: "main")
-k, --keep-history     Number of conversation history items to keep (default: 14)
```

### Example

```bash
# Analyze a C++ file using Claude o3-mini model
python run.py -c code/test.cpp -l o3-mini -k 15
```

This command will:
1. Load and parse `test.cpp`
2. Use the o3-mini model for vulnerability analysis
3. Maintain a context history of 15 items
4. Generate detailed reports of any findings

## 🏗️ Architecture

Baby Naptime is composed of several specialized components that work together:

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│    Agent    │────▶│ Code Browser│────▶│   Debugger  │
└─────┬───────┘     └─────────────┘     └─────────────┘
      │                                         ▲
      ▼                                         │
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│   Reporter  │◀────│  Scripter   │◀────│  Summarizer │
└─────────────┘     └─────────────┘     └─────────────┘
```

- **Agent**: Orchestrates the analysis workflow and manages LLM conversations
- **Code Browser**: Intelligently navigates code and extracts relevant segments
- **Debugger**: Provides GDB-based debugging with security analysis capabilities
- **Reporter**: Creates comprehensive vulnerability reports with evidence
- **Scripter**: Executes dynamic testing scripts to validate findings
- **Summarizer**: Maintains context efficiency by condensing conversation history

## 📊 Output

Results are stored in the `results/` directory with the following structure:

```
results/
├── [timestamp]_[filename]/
│   ├── vulnerability_report.md
│   ├── exploitation.py
│   ├── technical_findings.json
│   └── debug_logs/
```

## 🤝 Contributing

We welcome contributions from the security community! To contribute:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

See our [CONTRIBUTING.md](CONTRIBUTING.md) for more details.

## 📜 License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details.

## ⚠️ Disclaimer

Baby Naptime is intended for **educational and research purposes only**. Always obtain proper authorization before testing any system for vulnerabilities. The authors are not responsible for any misuse of this tool.

## 🙏 Acknowledgments

- Inspired by Google's Project Naptime
- Thanks to the open source security community
- All the security researchers who share knowledge freely

---

<p align="center">Made with ❤️ by security researchers who believe in automation for good</p>