# Coding Style Convention

| Code element                |           Convention           | Example                                                                 |
| --------------------------- | :----------------------------: | ----------------------------------------------------------------------- |
| Defines                     |      SCREAMING_SNAKE_CASE      | `#define PLATFORM_DESKTOP`                                              |
| Macros                      |      SCREAMING_SNAKE_CASE      | `#define MIN(A,B) (((A)<(B))?(A):(B))`                                  |
| Variables                   |           camelCase            | `int screenWidth = 0;`, `float targetFrameTime = 0.016f;`               |
| Constants                   |      SCREAMING_SNAKE_CASE      | `const int MAX_ITEMS = 8;`                                              |
| Pointers                    |         Type \*pointer         | `Texture2D *array = NULL;`                                              |
| float values                |              x.xf              | `float gravity = 0.09f`                                                 |
| Operators(\* /)             |         value1\*value2         | `int product = value*6;`, `int division = value/4;`                     |
| Operators(+ -)              |        value1 + value2         | `int sum = value + 10;`, `int res = value - 5;`                         |
| Operators(,)                |         value1, value2         | `int sum, total;`                                                       |
| Struct/Class/interface/Enum |           PascalCase           | `struct Texture2D`, `class Material`, `inteface Callable`, `enum Color` |
| Struct/Class members        |           camelCase            | `texture.width`, `color.r`                                              |
| Enum members                |      SCREAMING_SNAKE_CASE      | `Color::BLUE`, `Color::RED`, `ON`                                       |
| Functions(Standalone)       |           PascalCase           | `InitWindow()`, `LoadImageFromMemory()`                                 |
| Methods                     |           camelCase            | `v.distance()`, `s.length()`                                            |
| Functions params            |           camelCase            | `width`, `height`                                                       |
| Ternary Operator            | (condition)? result1 : result2 | `printf("Value is 0: %s", (value == 0)? "yes" : "no");`                 |
| Type Casting                |          (Type)value           | `int value = (int)3.1416f;`                                             |

Other conventions:

- All defined variables are ALWAYS initialized
- Four spaces are used, instead of TABS
- Trailing spaces are ALWAYS avoided
- Control flow statements and `break`/`continue` keywords are followed **by a space**:

```c
if (condition) value = 0;

while (!WindowShouldClose()) {

}

for (int i = 0; i < NUM_VALUES; i++) printf("%i", i);

switch (value) {
    case 0:
    // ...
    break;

    case 2:
    break;

    default:
    break;
}
```

- All conditions are always between parenthesis, but not boolean values:

```c
if ((value > 1) && (value < 50) && valueActive) {

}
```

- Curly braces are opened in the same line of the statement preceded by a space:

```c
void SomeFunction() {
   // TODO: Do something here!
}
```

- Empty body are defined in a single line:

```c
class SomeClass { };
```

## File Organization Conventions

| Item Type           |        Convention        | Example                                               |
| ------------------- | :----------------------: | ----------------------------------------------------- |
| Resource file       |      snake_case.ext      | `main_title.png`, `cubicmap.png`, `audio/gunshot.wav` |
| Directory name      |        snake_case        | `screens`, `characters`, `common_files`               |
| Root/Project name   |        PascalCase        | `FishInsulter`, `ExampleProject`                      |
| Source code files   |      PascalCase.ext      | `Main.c`, `GameplayScreen.c`, `PlayerController.java` |
| Documentation files | SCREAMING_SNAKE_CASE.ext | `README.md`, `CONTRIBUTING.md`, `LICENSE`             |

- `Build`/`Config` files (CMakeLists.txt, build.sh, config.json, Makefile) should be `snake_case` wherever possible, and may use standard naming conventions for the build system.
- Source code files are organized by functionality and usage in the app. Each file should contain a single class or a group of related functions.
- Resource files are organized by context and usage in the app. Loading requirements for data are also considered (grouping data when required).
- Descriptive names are used for the files, just reading the name of the file it should be possible to know what is that file and where it fits in the app.

```
resources/audio/fx/long_jump.wav
resources/audio/music/main_theme.ogg
resources/screens/logo/logo.png
resources/screens/title/title.png
resources/screens/gameplay/background.png
resources/characters/player.png
resources/characters/enemy_slime.png
resources/common/font_arial.ttf
resources/common/gui.png
```

### Project Directory Conventions

Standard C/C++ project directory structure:

```
ProjectName/
├── src/
│   ├── Main.c
│   ├── Game.c
│   └── Game.h
├── tests/
├── resources/
│   ├── background.png
│   └── font.ttf
├── libs/
│   └── libname/
├── docs/
│   ├── README.md
│   └── CONTRIBUTING.md
├── build/
│   └── Makefile
├── CMakeLists.txt
├── configure.sh
├── build.sh
├── LICENSE
├── README.md
├── .clang-format
└── .clang-tidy/
```

| Items         | Description                                            |
| ------------- | ------------------------------------------------------ |
| src/          | Source code files                                      |
| tests/        | Test files                                             |
| build/        | Compiled object files and binaries                     |
| resources/    | Resource/Assets files (textures, audio, fonts, etc.)   |
| docs/         | Documentation files (CONTRIBUTING.md, README.md, etc.) |
| libs/         | External libraries and dependencies                    |
| .clang-format | ClangFormat configuration file                         |
| configure.sh  | Project configuration script                           |
| build.sh      | Project build script                                   |

## Commenting & Documentation Conventions

- Use less comments, write code that is self-explanatory.
- Document all public functions and classes using Doxygen style comments.
