<h1>Отчёт:</h1> 

**Задача:**

Обработать графовую структуру в соответствии с заданным вариантом.
Обосновать выбор необходимого алгоритма и выбор структуры для представления
графов. Ввод данных осуществить на усмотрение программиста. Результат выдать в
графической форме.

**Задание:**

В системе двусторонних дорог за проезд
каждой дороги взимается некоторая пошлина.
Найти путь из города A в город B с
минимальной величиной S+P, где S - сумма
длин дорог пути, а P - сумма пошлин
проезжаемых дорог

**Цель работы** 

Цель работы - реализовать алгоритмы обработки графовых структур: поиск
различных путей.

**Введение:**

Наименование программы: lab_07.c

Краткие характеристики: Программа ищет путь из города A в город B с минимальной величиной S+P, где S - сумма длин дорог пути, а P - сумма пошлин проезжаемых дорог

Срок сдачи: 23.11.19  

**Основания для разработки:**

Заказчик: Александра Васильевна Силантьева

Заказчик: Никульшина Татьяна Александровна

Исполнитель: Сукочева Элис

**Требования к программе:**

1. Задача решается на языке программирования "с". 

2. При некорректном вводе пользователя выводится сообщение об ошибке.

3. Реализуется графический вывод графа.

**Входные данные**

1. Файл с графом.

2. Начальная вершина поиска.

3. Конечная вершина поиска.

**Выходные данные**

1. Самый кратчайший и бюджетный путь. 

2. Изображение графа.

3. Сообщения о некорректном вводе.

**Структура данных.**

```

    int matrix[LEN][LEN]; // матрица смежности

```

Матрица смежности matrix(n*n); В этой матрице элемент
matrix[i,j]= S + P, если ребро, связывающее вершины Vi и Vj существует и b[i,j]= бесконечность, если ребра
нет.Так как в моем варианте граф неориентированный, то матрица смежности симметрична.


**Тесты**


| Входные данные | Результат работы программы | 
|------------|----------| 
|dsvf|Сообщение о некорректном вводе|
|Несуществующие вершины|Сообщение о том, что данной вершины нет|
|Две существующие разные вершины |Минимальный путь, если он есть, иначе сообщение, о том, что данного пути нет|
|Одна и та же вершина|Название данной вершины|

**Аварийные ситуации**

1. При вводе символов, отличных от цифр, выдает сообщение об ошибки и завершает программу

![image](uploads/bb6e5584a67025e129eba26c2b01b515/image.png)

2. При вводе отрицательных или несуществующих индексов вывод о некорректном вводе индекса станции и просьба ввести заново (Также снова выводится список имеющихся станций)

![image](uploads/7b08fa90b9d53932e1a5723953adee41/image.png)


**Визуализация графа**

![image](uploads/f9204b861b61cca07da03b7145df755d/image.png)

**Алгоритм**

Для поиска кратчайших путей между всеми вершинами используется алгоритм
Флойда-Уоршалла. По алгоритму Флойда-Уоршалла сначала ищется кратчайший
путь от одной вершины ко всем вершинам, доступным из нее, затем проводятся те же
действия, но пытаясь пройти от этой вершины ко всем доступным из нее, проходя
каждый раз через новую вершину (сначала через первую, затем – через вторую и
т.д.). Таким образом обрабатываются все вершины.

**Ответы на вопросы**

1. Что такое граф?

Граф – это конечное множество вершин и ребер, соединяющих их, т. е.:
G = < V,E >,
где V – конечное непустое множество вершин; Е – множество ребер (пар
вершин).

2. Как представляются графы в памяти?

Графы в памяти могут представляться различным способом. Один из видов
представления невзвешенных графов – это матрица смежности B(n*n); В этой матрице элемент
b[i,j]=1, если ребро, связывающее вершины Vi и Vj существует и b[i,j]=0, если ребра
нет. У неориентированных графов матрица смежности всегда симметрична.

Во многих случаях удобнее представлять граф в виде так называемого списка
смежностей. Список смежностей содержит для каждой вершины из множества
вершин V список тех вершин, которые непосредственно связаны с этой вершиной.
Каждый элемент (ZAP[u]) списка смежностей является записью, содержащей данную
вершину и указатель на следующую запись в списке (для последней записи в списке
этот указатель – пустой). Входы в списки смежностей для каждой вершины графа
хранятся в таблице (массиве) (BEG [u])

3. Какие операции возможны над графами?

- Включение элемента

- Исключение элемента
 
- Обход графа


4. Какие способы обхода графов существуют?

Обход графа в глубину

Обход графа в ширину

5. Где используются грaфовые структуры?

Грaфовые структуры используются,к примеру, в задачах на пути (Схема дорог, метро, проезд между городами, странами, кратчайшая дорога от одной точки до другой и тд.) 

6. Какие пути в графе Вы знаете?

Эйлерова пути - когда граф имеет цикл, содержащий все рёбра графа по одному разу.

Гамильтонова пути - простой путь, проходящий через каждую вершину графа ровно 1 раз.

7. Что такое каркасы графа?

Дерево в кот-ром содержатся все вершины искомого графа и некоторые его рёбра. (Без циклов)

При использовании алгоритмов поисков в ширину и глубину графы обходят разными способами, получая при этом некоторые подграфы, которые имеют специфические названия: каркасы (остовы или стягивающие деревья).

**Вывод**

В этой лабораторной работе мы реализовали работу с графом. А точнее поиск минимального пути с помощью алгоритма Флойда-Уоршелла 
