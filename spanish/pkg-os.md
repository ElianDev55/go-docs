# Package `os` - Go Documentation

The `os` package provides a platform-independent interface to operating system functionality, including file and directory manipulation, process control, environment variables, and more.  
With `os`, you can work with the file system by opening, creating, reading, writing, and deleting files, managing directories, retrieving system info, and controlling program execution.

---

## Main Features Overview

| Title          | Description                                                                                | Code Signature                                                       | Usage Example                           |
| -------------- | ------------------------------------------------------------------------------------------ | -------------------------------------------------------------------- | --------------------------------------- | ------------------- |
| **Package os** | Library for OS-level operations: files, directories, processes, and environment variables. | `import "os"`                                                        | `file, err := os.Open("file.txt")`      |
| **File**       | Represents an open file descriptor.                                                        | `type File struct { ... }`                                           | `file.Stat()` to get file info          |
| **Open**       | Opens a file for reading only.                                                             | `func Open(name string) (*File, error)`                              | `f, err := os.Open("file.txt")`         |
| **Create**     | Creates a file for writing (overwrites if it exists).                                      | `func Create(name string) (*File, error)`                            | `f, err := os.Create("newfile.txt")`    |
| **OpenFile**   | Opens a file with specified flags and permissions.                                         | `func OpenFile(name string, flag int, perm FileMode) (*File, error)` | `os.OpenFile("file.txt", os.O_RDWR      | os.O_CREATE, 0666)` |
| **Stat**       | Returns file or directory information.                                                     | `func Stat(name string) (FileInfo, error)`                           | `info, err := os.Stat("file.txt")`      |
| **Remove**     | Deletes a file or empty directory.                                                         | `func Remove(name string) error`                                     | `os.Remove("file.txt")`                 |
| **Mkdir**      | Creates a directory with specified permissions.                                            | `func Mkdir(name string, perm FileMode) error`                       | `os.Mkdir("dir", 0755)`                 |
| **MkdirAll**   | Creates a directory and all necessary parents.                                             | `func MkdirAll(path string, perm FileMode) error`                    | `os.MkdirAll("a/b/c", 0755)`            |
| **ReadDir**    | Reads the contents of a directory and returns directory entries.                           | `func ReadDir(name string) ([]DirEntry, error)`                      | `entries, err := os.ReadDir("dir")`     |
| **Getwd**      | Gets the current working directory.                                                        | `func Getwd() (string, error)`                                       | `cwd, err := os.Getwd()`                |
| **Chdir**      | Changes the current working directory.                                                     | `func Chdir(dir string) error`                                       | `os.Chdir("/tmp")`                      |
| **Exit**       | Terminates the program with an exit code.                                                  | `func Exit(code int)`                                                | `os.Exit(1)`                            |
| **Args**       | Slice holding command-line arguments.                                                      | `var Args []string`                                                  | `os.Args[1]`                            |
| **Environ**    | Returns a slice of environment variables in "key=value" format.                            | `func Environ() []string`                                            | `env := os.Environ()`                   |
| **Getenv**     | Retrieves the value of an environment variable.                                            | `func Getenv(key string) string`                                     | `val := os.Getenv("PATH")`              |
| **Setenv**     | Sets the value of an environment variable.                                                 | `func Setenv(key, value string) error`                               | `os.Setenv("MYVAR", "value")`           |
| **Unsetenv**   | Removes an environment variable.                                                           | `func Unsetenv(key string) error`                                    | `os.Unsetenv("MYVAR")`                  |
| **TempDir**    | Returns the default directory for temporary files.                                         | `func TempDir() string`                                              | `tmp := os.TempDir()`                   |
| **IsNotExist** | Checks if an error indicates a file or directory does not exist.                           | `func IsNotExist(err error) bool`                                    | `os.IsNotExist(err)`                    |
| **FileMode**   | Type representing file mode and permission bits.                                           | `type FileMode uint32`                                               | `os.FileMode(0755)`                     |
| **FileInfo**   | Interface describing file or directory metadata.                                           | `type FileInfo interface { ... }`                                    | `info.Mode(), info.Name(), info.Size()` |

---

For complete and official documentation, visit [pkg.go.dev/os](https://pkg.go.dev/os).

---

Would you like me to create separate tables for types, functions, and variables? Or is this format good for you?
