# Baby Naptime 🍼

An open source implementation inspired by Google's Project Naptime - an automated vulnerability analysis tool that uses Large Language Models (LLMs) to discover and exploit native vulnerabilities.

## Overview

Baby Naptime is a sophisticated security analysis tool that leverages LLMs to:
- Perform intelligent vulnerability analysis
- Generate automated exploits
- Detect memory corruption issues
- Provide advanced debugging capabilities

The name comes from the idea that you can find bugs while the baby's sleeping! 👶

## Features

- **Intelligent Analysis**: Uses LLMs to understand code context and identify potential vulnerabilities
- **Automated Exploitation**: Generates and tests exploit payloads automatically
- **Memory Analysis**: Deep inspection of memory layout and corruption patterns
- **Advanced Debugging**: Integrated GDB-based debugging with security focus
- **Code Navigation**: Smart code browsing and function analysis
- **Reporting**: Detailed vulnerability reports with exploitation details

## Requirements

- Python 3.7+
- GDB debugger
- C/C++ compiler (g++)
- OpenAI API key
- Required Python packages (see `requirements.txt`)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/baby-naptime.git
cd baby-naptime
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Set up your OpenAI API key:
```bash
export OPENAI_API_KEY='your-api-key-here'
```

## Usage

Basic usage:
```bash
python run.py -c <code_file> [options]
```

Options:
- `-c, --code_file`: Path to the source code file to analyze (required)
- `-d, --code-directory`: Directory containing additional source files (default: ".")
- `-m, --max-iterations`: Maximum number of analysis iterations (default: 100)
- `-l, --llm-model`: LLM model to use (choices: gpt-3.5-turbo, gpt-4o, gpt-4o-mini, o3-mini, o1-preview)
- `-f, --main-function`: Entry function to begin analysis (default: "main")
- `-k, --keep-history`: Number of conversation history items to keep (default: 14)

## Architecture

The project consists of several key components:

- **Agent**: Orchestrates the analysis workflow and maintains conversation with LLM
- **Code Browser**: Navigates and extracts code segments for analysis
- **Debugger**: Provides GDB-based debugging capabilities
- **Reporter**: Generates detailed vulnerability reports
- **Scripter**: Executes Python scripts for testing
- **Summarizer**: Maintains context by summarizing conversation history

## Example

```bash
python run.py -c code/test.cpp -l o3-mini -k 15
```

This will:
1. Analyze test.cpp for vulnerabilities
2. Use the o3-mini model for LLM analysis
3. Keep 15 conversation items in context
4. Generate a report if vulnerabilities are found

## Output

Results are stored in the `results/` directory:
- Vulnerability summary reports (markdown)
- Exploitation details
- Technical findings

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Disclaimer

This tool is for educational and research purposes only. Always obtain proper authorization before testing any system for vulnerabilities.

## Acknowledgments

Inspired by Google's Project Naptime and the security research community.

---
Made with ❤️ by security researchers who love automation