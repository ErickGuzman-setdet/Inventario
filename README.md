# Gestión de Inventario con Apuntadores en C++

Este es un pequeño proyecto personal que realicé en una materia, Algoritmos y Estructuras de Datos. Durante este proyecto se optó por una estructura sencilla de nodos enlazados; esta estructura nos permite ir conectando, por así decirlo, un nodo con otro nodo.

El nodo puede contener datos específicos; en este caso, como está basado en una tienda, tenemos un ID que es el que nos indica el producto, el nombre del producto, la cantidad que tenemos de ese mismo producto y el precio.

---

## Declaración del nodo

    '''
        class Producto{
            public:
                int ID;
                string Nombre;
                int Cant_Stock;
                double Precio;

                Producto *siguiente;
                Producto(int ID, string Nombre, int Cant_Stock, double Precio)
                : ID(ID), Nombre(Nombre), Cant_Stock(Cant_Stock), Precio(Precio), siguiente(NULL) {}
        };
    '''

Gracias a esta forma de manejar los datos, es que nosotros podemos agregar, eliminar, modificar precio o cantidad, e incluso localizar algún producto mediante su ID. Por lo tanto, este programa hace lo siguiente:

    * Inserción de productos
    * Eliminación de productos
    * Modificación de productos
    * Muestreo de productos (en stock y precio)
    * Búsqueda de producto por ID
    * Guardar datos en CSV

# Requisitos para lanzar este script en C++

    Para ello necesitamos algún compilador de C/C++. Existen programas como:

    Dev-C++: https://sourceforge.net/projects/orwelldevcpp/

    Visual Studio Code: https://code.visualstudio.com/

    En lo personal me gusta un poco más Visual Studio Code, pero para poder instalar C/C++ en Visual Studio Code no basta con descargarlo desde el visual, sino que también necesitamos el MinGW, que es un entorno de desarrollo que nos permite compilar, enlazar y ejecutar programas en C/C++ nativamente en Windows:

    MinGW: https://sourceforge.net/projects/mingw-w64/

Una vez instalado y ejecutado ya sea en Dev o en Visual, nos genera un .exe que es el mismo código pero compilado. Ya no hay necesidad de abrir el compilador, simplemente ejecutamos directamente el .exe y podemos gestionar desde ahí.

Aunque cada vez que se cierra el programa se borra la información que se agrega, para ello se implementó el guardado con CSV, que es un archivo en Excel. Ahora, contestando la pregunta de por qué se borra la información al cerrar el programa, la respuesta es bastante sencilla: como estamos manejando espacios de memoria para almacenar la información en la memoria RAM mediante los apuntadores, al cerrar el programa se pierde esa información y no hay manera de volver a ella. Al reiniciar o apagar el dispositivo, se borra toda esa información para liberar memoria y que el sistema vuelva a arrancar de manera normal.
