# Paquete `os` - Documentación en Go

El paquete `os` proporciona una interfaz independiente del sistema operativo para funciones básicas de entrada/salida, manejo de archivos, directorios, procesos, variables de entorno y más.  
Con `os` puedes interactuar con el sistema de archivos, abrir, crear, leer, escribir y eliminar archivos, gestionar directorios, obtener información del sistema y controlar la ejecución del programa.

---

## Resumen de funcionalidades principales

| Título           | Descripción                                                                                     | Código                                      | Ejemplo de uso                                     |
|------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------|--------------------------------------------------|
| **Package os**   | Biblioteca para operaciones del sistema operativo: archivos, directorios, procesos y variables. | `import "os"`                              | `file, err := os.Open("archivo.txt")`             |
| **File**         | Representa un descriptor de archivo abierto.                                                   | `type File struct { ... }`                   | `file.Stat()` para obtener información del archivo|
| **Open**         | Abre un archivo solo para lectura.                                                             | `func Open(name string) (*File, error)`     | `f, err := os.Open("archivo.txt")`                 |
| **Create**       | Crea un archivo para escritura, sobrescribiendo si existe.                                     | `func Create(name string) (*File, error)`   | `f, err := os.Create("nuevo.txt")`                 |
| **OpenFile**     | Abre un archivo con flags y permisos específicos.                                              | `func OpenFile(name string, flag int, perm FileMode) (*File, error)` | `os.OpenFile("archivo.txt", os.O_RDWR|os.O_CREATE, 0666)` |
| **Stat**         | Obtiene información de un archivo o directorio.                                               | `func Stat(name string) (FileInfo, error)`  | `info, err := os.Stat("archivo.txt")`              |
| **Remove**       | Elimina un archivo o directorio vacío.                                                        | `func Remove(name string) error`             | `os.Remove("archivo.txt")`                          |
| **Mkdir**        | Crea un directorio con permisos específicos.                                                  | `func Mkdir(name string, perm FileMode) error` | `os.Mkdir("directorio", 0755)`                      |
| **MkdirAll**     | Crea un directorio y todos los padres necesarios.                                            | `func MkdirAll(path string, perm FileMode) error` | `os.MkdirAll("a/b/c", 0755)`                       |
| **ReadDir**      | Lee el contenido de un directorio y devuelve las entradas.                                   | `func ReadDir(name string) ([]DirEntry, error)` | `entries, err := os.ReadDir("directorio")`         |
| **Getwd**        | Obtiene el directorio de trabajo actual.                                                     | `func Getwd() (string, error)`               | `cwd, err := os.Getwd()`                            |
| **Chdir**        | Cambia el directorio de trabajo actual.                                                     | `func Chdir(dir string) error`                | `os.Chdir("/tmp")`                                  |
| **Exit**         | Finaliza el programa con un código de salida.                                               | `func Exit(code int)`                         | `os.Exit(1)`                                        |
| **Args**         | Slice con los argumentos de línea de comandos.                                              | `var Args []string`                           | `os.Args[1]`                                        |
| **Environ**      | Devuelve las variables de entorno en formato `key=value`.                                   | `func Environ() []string`                     | `env := os.Environ()`                               |
| **Getenv**       | Obtiene el valor de una variable de entorno.                                               | `func Getenv(key string) string`             | `val := os.Getenv("PATH")`                          |
| **Setenv**       | Establece el valor de una variable de entorno.                                             | `func Setenv(key, value string) error`       | `os.Setenv("VAR", "valor")`                         |
| **Unsetenv**     | Elimina una variable de entorno.                                                           | `func Unsetenv(key string) error`             | `os.Unsetenv("VAR")`                                |
| **TempDir**      | Devuelve el directorio temporal del sistema operativo.                                     | `func TempDir() string`                       | `tmp := os.TempDir()`                               |
| **IsNotExist**   | Comprueba si un error indica que un archivo o directorio no existe.                         | `func IsNotExist(err error) bool`             | `os.IsNotExist(err)`                                |
| **FileMode**     | Tipo que representa los permisos y modos de archivo.                                       | `type FileMode uint32`                        | `os.FileMode(0755)`                                 |
| **FileInfo**     | Interface con información sobre un archivo o directorio.                                  | `type FileInfo interface { ... }`             | `info.Mode(), info.Name(), info.Size()`             |

---

Puedes encontrar la documentación oficial y completa en [pkg.go.dev/os](https://pkg.go.dev/os).

---

¿Quieres que te prepare una tabla separada para tipos, funciones y variables o así te queda perfecto?
