# quiz9Datos

Este documento contiene el funcionamiento de los algoritmos implementadas y como ejecutarlos usando grafos de prueba.

---
# Estructura del proyecto:
-src:  <br>
--DemoMST.java <br>
--Graph.java <br>
--MSTSolver.java <br>
-Quiz 8 Algoritmos a mano.pdf <br>

El archivo `DemoMST`es el correspondiente para uso de pruebas, en este se pueden inicializar objetos de tipo `Graph` así como la clase estática `MSTSolver` para ejecutar los algoritmos de Prim y Kruskal.
Por otra parte el pdf `Quiz 8 Algoritmos a manoQuiz 8 Algoritmos a mano` corresponde al cálculo hecho a mano de los algoritmos, en todo caso sea ejecutado el caso de prueba pre-cargado debería tener los mismos resultados que se encuentran en este archivo.

# Cargar pruebas:
En caso de querer crear casos de prueba se deben seguir los siguientes pasos: <br>
1.Crear un arreglo con el valor de los vértices. <br>
2.Inicializar un nuevo objeto Graph con la cantidad de vértices. <br>
3.Agregar los pesos entre los vértices utilizando la siguiente notación (Vorigen,Vdestino,peso) <br>
**Example:**
```java
String[] vertex = {"A", "B", "C", "D"}; //Creación del arreglo
Graph graph = new Graph(vertex.length); //Inicialización del objeto
//Agregar aristas.
graph.addEdge(0,1,2)
graph.addEdge(0,2,3)
graph.addEdge(2,3,1)
graph.addEdge(1,3,2)
```
Una vez tengamos el o los nodos listos utilizamos el objeto de `MSTSolver` previamente instanciado, y podemos ejecutar el algoritmo de Prim, Kruskal o ambos; pasando como argumento el grafo previamente creado. <br>
**Example:**
```java
MSTSolver solver = new MSTSolver(); //Instanciamos MSTSolver

List<MSTSolver.MSTEdge> primResults = solver.prim(graph);
mostrarMst(primResults, labels);

List<MSTSolver.MSTEdge> kruskalResult = solver.kruskal(graph);
mostrarMst(kruskalResult, labels);
```

Ambos algoritmos se encargaran de crear el MST como una lista de aristas y gracias a la función mostrarMst se despliegan los datos como la estructura del grafo, y la cantidad de aristas junto el peso total.

