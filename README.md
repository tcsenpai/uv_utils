# uv_utils

uv_utils is a collection of utilities for the [UV project](https://github.com/astral-sh/uv).

## Disclaimer

This project is not affiliated with the UV project.
This project, while tested and used by the author, is not guaranteed to work for everyone. Please try to understand the code before using it.

## Prerequisites

- [uv](https://github.com/astral-sh/uv) and related dependencies

## Installation

```bash
git clone https://github.com/tcsenpai/uv_utils.git
cd uv_utils
chmod +x uv*
```

It is recommended to add the uv_utils directory to your PATH environment variable or to move the executable files to a directory in your PATH.

## Features and Usage

### uvc

uvc is a utility for converting a python's requirements.txt-like file to a fully fledged uv project.

```bash
uvc requirements.txt # replace requirements.txt with your requirements.txt-like file as needed
```

This will create a pyproject.toml file in the current directory, manage the empty hello.py file safely (backing up any existing hello.py file), and add the necessary dependencies to the pyproject.toml file; it will also automate the creation of a .venv directory and install the dependencies into it using uv.

You can now run the project using uv (included `uv run`, `uv sync`, `uv add`, etc.)

**Note:** You can use uvr (see below) to run the project without specifying the file name each time.

### uvr

uvr is a utility for running a uv project without specifying the file name each time.

#### First Run

```bash
uvr name_of_your_entry_file.py
```

This will create a uvr.toml file in the current directory, which will store the name of the entry file.

#### Subsequent Runs

```bash
uvr
```

This will run the entry file specified in the uvr.toml file.

## Under the Hood

All the files are written in plain bash, and are designed to be as simple as possible.
Also, the utilities are designed to be wrappers around `uv` commands, so that full compatibility is maintained.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
