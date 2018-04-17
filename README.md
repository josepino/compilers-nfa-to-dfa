#-----------------------------------------------------------
### DISEÑO DE COMPILADORES - COMPILERS DESIGN
# Conversión de un AFN a un AFD
# Minimización del AFD resultante
#-----------------------------------------------------------


### Consideraciones
1) Se asume que ya se tiene el resultado de Thompson, luego de aplicar a una expresion regular.
2) El archivo de ejemplo "ClaseAFN-1.txt" que está en el directorio "Data" contiene un AFN que representa el resultado de la expresion regular "(a|b)*abb"
3) Se adjunta un PDF con la gráfica, proceso y resultado.



#---------------------------------------------------------------------------------------------------------------
### Funciones:

1) Lectura y escritura de archivos
2) Conversión de AFN a AFD
    a) Lee un archivo y guarda en otro. El comando es python app.py <minimizar> o <afd> seguido del <archivo de origen> y luego el <destino>.
    b) Ejemplo: ```python app.py afd Data/ClaseAFN-1.txt Data/ClaseAFN-1-ResultadoLun1.txt```

3) Minimización de AFD
    a) Minimiza un AFD leído desde un archivo.
    b) Ejemplo: ```python app.py minimizar Data/ClaseAFN-1-ResultadoLun1.txt Data/ClaseAFN-1-ResultadoLun1-Min.txt```
#---------------------------------------------------------------------------------------------------------------





### Formato de los AF (Autómatas Finitos)

A) Cada linea representa un nodo y tiene varios parametros separados por espacio
  1) Primer parametro: 
        Nombre del nodo. 
  2) Segundo parametro: 
        Nodo final. Identifica si e nodo es final con una "S" si lo es o una "N" en caso contrario.
  3) Siguientes parametros: 
        Transiciones. Las transiciones se definen como ```simbolo:nodo```, sin espacios. 
        El simbolo "E" se usa para la palabra vacía.

El primer nodo del archivo se asumirá como el nodo inicial.

Ejemplo de AF en archivo luego de aplicar Thompson para la expresion regular (a|b)*abb :
0 N E:1 E:7
1 N E:2 E:4
2 N a:3
3 E:6
4 b:5
5 E:6
6 E:1 E:7
7 a:8
8 b:9
9 b:10
10 S




### Fuentes/Basado en:
https://github.com/jpverdejo/plf
https://www.youtube.com/watch?v=Wtv6t_UafJo
https://www.youtube.com/watch?v=NF47BSorRfU
https://github.com/osandov/pylex
https://xysun.github.io/posts/regex-parsing-thompsons-algorithm.html
https://github.com/sveraaquino/analizador_lexico/blob/master/subconjunto.py
http://sisbib.unmsm.edu.pe/bibvirtualdata/publicaciones/indata/Vol6_n1/pdf/conversion.pdf




# compilers-nfa-to-dfa
