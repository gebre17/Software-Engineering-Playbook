# Python Utility Scripts

A collection of lightweight utility scripts and boilerplates for quick deployment and execution.

## 1. Structured CLI Utility (using `argparse`)

```python
#!/usr/bin/env python3
"""
Description: Example boilerplate for CLI utility scripts.
Usage: python script.py -n "John" -v
"""

import argparse
import sys

def parse_arguments():
    parser = argparse.ArgumentParser(description="A clean CLI template.")
    parser.add_argument("-n", "--name", required=True, help="Name of target")
    parser.add_argument("-v", "--verbose", action="store_true", help="Enable verbose logs")
    return parser.parse_args()

def main():
    args = parse_arguments()
    if args.verbose:
        print(f"[LOG] Verbose mode enabled. Processing {args.name}...")
    
    print(f"Hello, {args.name}!")
    return 0

if __name__ == "__main__":
    sys.exit(main())
```

## 2. Directory Size Audit Script

```python
from pathlib import Path

def audit_directory(dir_path):
    target = Path(dir_path)
    if not target.is_dir():
        print(f"{dir_path} is not a directory.")
        return
        
    for item in target.iterdir():
        if item.is_file():
            print(f"File: {item.name} | Size: {item.stat().st_size} bytes")
        elif item.is_dir():
            dir_size = sum(f.stat().st_size for f in item.glob('**/*') if f.is_file())
            print(f"Folder: {item.name}/ | Total Size: {dir_size} bytes")
```
