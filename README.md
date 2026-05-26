# Codere

[![PyPI version](https://badge.fury.io/py/codere.svg)](https://pypi.org/project/codere/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## A Universal Code Library Supporting All Programming Languages

**Codere** is a Python library that provides utilities and tools for working with code in various programming languages. It supports Python, Java, JavaScript, TypeScript, Ruby, PHP, HTML, CSS, JSON, React, and many more!

## Features

- 🌍 **Multi-Language Support**: Works with 40+ programming languages
- 🔍 **Language Detection**: Automatically detect the programming language of code snippets
- 📊 **Code Analysis**: Process and analyze code from different languages
- 🎨 **Code Formatting**: Basic formatting utilities for various languages
- 🚀 **Easy to Use**: Simple and intuitive API

## Supported Languages

Codere supports a wide range of programming languages including:

- **Web**: Python, Java, JavaScript, TypeScript, PHP, Ruby
- **Frontend**: HTML, CSS, React, JSX
- **Data**: JSON, XML, YAML, TOML, SQL
- **Systems**: C, C++, Rust, Go, Swift, Kotlin
- **Functional**: Haskell, Elixir, Clojure, Scala, F#
- **Scripting**: Perl, Lua, Shell, PowerShell
- **Other**: C#, VB, Delphi, Assembly, MATLAB, R, Solidity, Verilog, VHDL, Markdown, LaTeX

And many more!

## Installation

### From PyPI (coming soon)

```bash
pip install codere
```

### From GitHub

```bash
pip install git+https://github.com/codere/codere.git
```

### Local Installation

```bash
git clone https://github.com/codere/codere.git
cd codere
pip install -e .
```

## Usage

### Basic Usage

```python
from codere import CodeProcessor, LanguageDetector, CodeFormatter

# Detect programming language
detector = LanguageDetector()
code = '''
def hello():
    print("Hello, World!")
'''
language = detector.detect(code)
print(f"Detected language: {language}")  # Output: python

# Process code
processor = CodeProcessor()
result = processor.process(code)
print(result)
# Output: {'language': 'python', 'length': 38, 'lines': 4, 'status': 'processed'}

# Format code
formatter = CodeFormatter()
formatted = formatter.format(code, "python")
print(formatted)
```

### Advanced Usage

```python
from codere import get_supported_languages
from codere.utils import detect_language, count_lines, get_file_extension

# Get all supported languages
languages = get_supported_languages()
print(f"Supported languages: {len(languages)}+")

# Detect language from code snippet
js_code = """
function greet(name) {
    console.log(`Hello, ${name}!`);
}
"""
lang = detect_language(js_code)
print(f"Language: {lang}")  # Output: javascript

# Count lines in code
line_count = count_lines(js_code)
print(f"Lines: {line_count}")

# Get file extension
ext = get_file_extension("python")
print(f"Python extension: {ext}")  # Output: .py
```

## Examples

### Example 1: Multi-language Code Analysis

```python
from codere import CodeProcessor

processor = CodeProcessor()

# Python code
python_code = """
class MyClass:
    def __init__(self):
        pass
"""
result = processor.process(python_code, "python")
print(result)

# JavaScript code
js_code = """
const myFunc = () => {
    return 'Hello';
}
"""
result = processor.process(js_code, "javascript")
print(result)
```

### Example 2: Automatic Language Detection

```python
from codere import LanguageDetector

detector = LanguageDetector()

samples = [
    ("public class Main {}", "java"),
    ("<?php echo 'Hi'; ?>", "php"),
    ("<div>Hello</div>", "html"),
    ("body { color: red; }", "css"),
]

for code, expected in samples:
    detected = detector.detect(code)
    print(f"Expected: {expected}, Detected: {detected}")
```

## Development

### Setup Development Environment

```bash
# Clone the repository
git clone https://github.com/codere/codere.git
cd codere

# Install development dependencies
pip install -e ".[dev]"

# Run tests
pytest

# Code formatting
black src/ tests/

# Linting
flake8 src/ tests/
```

### Running Tests

```bash
pytest tests/ -v
```

## Project Structure

```
codere/
├── src/
│   └── codere/
│       ├── __init__.py      # Main module
│       └── utils.py         # Utility functions
├── tests/                   # Test suite
├── pyproject.toml          # Project configuration
├── README.md               # This file
└── LICENSE                 # MIT License
```

## Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Roadmap

- [ ] Add more language-specific formatters
- [ ] Implement syntax highlighting
- [ ] Add code compilation support
- [ ] Integrate with popular IDEs
- [ ] Add more code analysis features
- [ ] Support for additional programming languages

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Authors

- Codere Team

## Acknowledgments

- Thanks to all contributors who have helped shape this library
- Inspired by the need for multi-language code tools

## Contact

- Project Link: [https://github.com/codere/codere](https://github.com/codere/codere)
- PyPI: [https://pypi.org/project/codere](https://pypi.org/project/codere)

---

Made with ❤️ for developers worldwide
