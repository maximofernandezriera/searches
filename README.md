# Más algoritmos de ordenación (agarros que vienen curvas)
### Selección
El algoritmo de [selección](https://es.wikipedia.org/wiki/Ordenamiento_por_selecci%C3%B3n). su eficiencia es de O(n²).  Consiste en ir buscando el elemento más pequeño del array y colocarlo en la primera posición, luego el segundo más pequeño y colocarlo en la segunda posición, y así sucesivamente. Este método es más eficiente que el método de la burbuja, ya que solo hace una comparación por cada iteración. En definitiva, en cada iteración, se selecciona el menor elemento del subarray no ordenado y se intercambia con el primer elemento de este subarray.
- https://www.youtube.com/watch?v=Ns4TPTC8whw
- https://podcast.uc3m.es/videos/2017/02/p1b9g9un9q1tad1924187c1f60on04.mp4

![imagen](https://upload.wikimedia.org/wikipedia/commons/9/94/Selection-Sort-Animation.gif)

```java
public class Main {
    public static void seleccion(int[] array) {
        int aux;
        int min;
        for (int i = 0; i < array.length; i++) {
            min = i;
            for (int j = i + 1; j < array.length; j++) {
                if (array[j] < array[min]) {
                    min = j;
                }
            }
            aux = array[i];
            array[i] = array[min];
            array[min] = aux;
        }
    }

    public static void main(String[] args) {
        int[] array = {64, 34, 25, 12, 22, 11, 90};
        seleccion(array);
        for (int value : array) {
            System.out.print(value + " ");
        }
    }
}
```

### Inserción
El algoritmo de [insercción](https://es.wikipedia.org/wiki/Ordenamiento_por_inserci%C3%B3n). Su eficiencia es O(n²). Es decir, el tiempo de ejecución es proporcional al cuadrado del tamaño del array. Inicialmente se tiene un solo elemento, que obviamente es un conjunto ordenado. Después, cuando hay k elementos ordenados de menor a mayor, se toma el elemento k+1 y se compara con todos los elementos ya ordenados, deteniéndose cuando se encuentra un elemento menor (todos los elementos mayores han sido desplazados una posición a la derecha) o cuando ya no se encuentran elementos (todos los elementos fueron desplazados y este es el más pequeño). En este punto se inserta el elemento k+1 debiendo desplazarse los demás elementos. En definitiva, nn cada iteración, se selecciona el menor elemento del subarray no ordenado y se intercambia con el primer elemento de este subarray.
- https://www.youtube.com/watch?v=ROalU379l3U
- https://youtu.be/8NMKDMl4_4w?si=CDIZ-AbbANqXTHyL

![imagen](https://upload.wikimedia.org/wikipedia/commons/0/0f/Insertion-sort-example-300px.gif)

```java
public class Main {
    public static void insercion(int[] array) {
        int aux, j;
        for (int i = 1; i < array.length; i++) {
            aux = array[i];
            j = i - 1;
            while (j >= 0 && array[j] > aux) {
                array[j + 1] = array[j];
                j--;
            }
            array[j + 1] = aux;
        }
    }

    public static void main(String[] args) {
        int[] array = {64, 34, 25, 12, 22, 11, 90};
        insercion(array);
        for (int value : array) {
            System.out.print(value + " ");
        }
    }
}
```
