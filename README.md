# Gemini CLI Configuration
This repository contains my universal engineering guidelines for the Gemini CLI.

## Why Public?
I am making this repository public intentionally to allow for easy portability and synchronization across multiple development environments and machines. It ensures my engineering standards and Gemini behaviors remain consistent wherever I work.

## Installation on new machines
```bash
git clone https://github.com/pju-hoge/.gemini pju-hoge-gemini && { [ -e ~/.gemini/GEMINI.md ] && echo "Error: ~/.gemini/GEMINI.md already exists" && exit 1 || ln -s ~/pju-hoge-gemini/GEMINI.md ~/.gemini/GEMINI.md; }
```
