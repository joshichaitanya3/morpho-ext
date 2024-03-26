# morpho-ext

Code to setup boilerplate for Morpho extensions.

To create the directory structure and basic files for your extension called `myextension`, run

```bash
python morpho-ext.py myextension
```

This will generate a directory called `morpho-myextension` in the working directory with the following structure:

```
morpho-myextension
.
├── README.md
├── examples
│   └── myextension_example.morpho
├── share
│   ├── help
│   │   └── myextension.md
│   └── modules
│       └── myextension.morpho
└── test
    └── myextension_test.morpho
```

You can pass an optional `--lang` argument with the choices `morpho` and `c`. The default is `morpho`, for creating modules written in Morpho itself. For a C-based extension to be compiled as a dynamic library, run 

```bash
python morpho-ext.py my-c-ext --lang c
```

This will generate the following directories and files:
```
.
├── .gitignore
├── CMakeLists.txt
├── README.md
├── examples
│   └── my-c-ext_example.morpho
├── lib
│   └── .gitignore
├── share
│   ├── help
│   │   └── my-c-ext.md
│   └── modules
│       └── my-c-ext.morpho
├── src
│   ├── CMakeLists.txt
│   ├── my-c-ext.c
│   └── my-c-ext.h
└── test
    └── my-c-ext_test.morpho
```

To call this script from anywhere, run the command
```bash
chmod +x morpho-ext.py
```
to make the file an executable, then add it to the PATH variable in your bashrc or zshrc:
```bash
export PATH=/path/to/script:$PATH
```

>Note: The `/path/to/script` doesn't contain the filename, and terminates at the directory.
