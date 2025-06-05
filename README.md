# HTTP
Libreria C para crear WebService JSON.
Compilada usando: `go build -o HTTP.dll -buildmode=c-shared HTTP.go`

---

### 📥 Descargar la librería

| Linux | Windows |
| --- | --- |
| `wget https://github.com/IngenieroRicardo/HTTP/releases/download/1.0/HTTP.so` | `Invoke-WebRequest https://github.com/IngenieroRicardo/HTTP/releases/download/1.0/HTTP.dll -OutFile ./HTTP.dll` |
| `wget https://github.com/IngenieroRicardo/HTTP/releases/download/1.0/HTTP.h` | `Invoke-WebRequest https://github.com/IngenieroRicardo/HTTP/releases/download/1.0/HTTP.h -OutFile ./HTTP.h` |

---

### 🛠️ Compilar

| Linux | Windows |
| --- | --- |
| `gcc -o main.bin main.c ./HTTP.so` | `gcc -o main.exe main.c ./HTTP.dll` |
| `x86_64-w64-mingw32-gcc -o main.exe main.c ./HTTP.dll` |  |

---

### 🧪 Ejemplo básico para leer HTTP

```C

```

---

### 🧪 Ejemplo para escribir, editar y eliminar HTTP

```C

```

---

### 🧪 Ejemplo avanzado para leer HTTP

```C

```

---



## 📚 Documentación de la API

### Funciones Principales

#### Manejo Básico de HTTP
- `HTTPResult ParseHTTP(const char* HTTP_str)`: Analiza una cadena HTTP
- `int IsValidHTTP(const char* HTTP_str)`: Verifica si una cadena es HTTP válido

#### Obtención de Valores
- `HTTPResult GetHTTPValue(const char* HTTP_str, const char* key)`: Obtiene valor por clave
- `HTTPResult GetHTTPValueByPath(const char* HTTP_str, const char* path)`: Obtiene valor por ruta
- `HTTPResult GetArrayLength(const char* HTTP_str)`: Obtiene longitud de array
- `HTTPResult GetArrayItem(const char* HTTP_str, int index)`: Obtiene elemento de array

#### Construcción/Modificación
- `HTTPResult CreateEmptyHTTP()`: Crea objeto HTTP vacío
- `HTTPResult CreateEmptyArray()`: Crea array HTTP vacío
- `HTTPResult AddStringToHTTP(const char* HTTP_str, const char* key, const char* value)`
- `HTTPResult AddNumberToHTTP(const char* HTTP_str, const char* key, double value)`
- `HTTPResult AddBooleanToHTTP(const char* HTTP_str, const char* key, int value)`
- `HTTPResult AddHTTPToHTTP(const char* parent_HTTP, const char* key, const char* child_HTTP)`
- `HTTPResult AddItemToArray(const char* HTTP_array, const char* item)`
- `HTTPResult RemoveKeyFromHTTP(const char* HTTP_str, const char* key)`
- `HTTPResult RemoveItemFromArray(const char* HTTP_array, int index)`
- `HTTPResult MergeHTTP(const char* HTTP1, const char* HTTP2)`: Combina dos HTTPs

#### Utilidades
- `void FreeHTTPResult(HTTPResult result)`: Libera memoria de resultados
- `void FreeHTTPArrayResult(HTTPArrayResult result)`: Libera memoria de arrays

### Estructuras
```c
typedef struct {
    char* value;      // Valor obtenido
    int is_valid;     // 1 si es válido, 0 si hay error
    char* error;      // Mensaje de error (si lo hay)
} HTTPResult;

typedef struct {
    char** items;     // Array de elementos
    int count;        // Número de elementos
    int is_valid;     // 1 si es válido, 0 si hay error
    char* error;      // Mensaje de error (si lo hay)
} HTTPArrayResult;
```
