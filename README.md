class Node

Узел дерева. Узел правильный, если его Address правильный.

 

Node

1.       Свойства

1.1.          Address

1.2.          AddressAsString

1.3.          Children

1.4.          IsCorrect

1.5.          Level

1.6.          Name

1.7.          Number

1.8.          Parent

2.       Конструкторы

3.       Делегаты

4.       Методы

 

Примеры

 

 

 

1.     Свойства

 

1.1.          List<int> Address { get; set; }

Адрес узла в дереве. Последовательность (...,n2,n1,n0), где n – Number. n0 принадлежит этому узлу, остальные элементы принадлежат его предкам: n1 – к родителю, n2 – к прародителю и т.д., первый элемент – к первопредку. Если последовательность содержит один элемент, то соответствующий узел не имеет предков. Address должен быть уникален в пределах дерева. Address правильный, если описывает положение узла в дереве. На Address может ссылаться только один узел. "set;" нужен для того, чтобы создавать локальные деревья. После обработки локальные деревья вписываются в нужное место других деревьев.

 

1.2.          string AddressAsString { get; set; }

Address в виде "(...,n2,n1,n0)".

 

1.3.          List<Node> Children { get; }

Потомки этого узла.

 

1.4.          bool IsCorrect { get; }

Результат проверки правильности этого узла.

 

1.5.          int Level { get; }

Уровень иерархии дерева, на котором находится этот узел. Количество предков этого узла, служащее общим признаком узлов, объединяющим их в поколение. Узлы на уровне L являются следующим поколением по отношению к узлам на уровне L-1.

 

1.6.          string Name { get; set; }

Имя этого узла. На Level дерева должны быть узлы с уникальными именами. Имена в отличие от Address нельзя задавать любые, т.к. невозможно создать метод автоматического исправления имен.

 

1.7.          int Number { get; }

Номер этого узла на его Level.

 

1.8.          Node Parent { get; }

Родитель этого узла.

 

2.       Конструкторы

 

2.1.          ()

2.2.          (string name)

2.3.          (int[] address)

2.4.          (List<int> address)

2.5.          (List<Node> children)

2.6.          (string name, string address)

2.7.          (string name, int[] address)

2.8.          (string name, List<int> address)

2.9.          (string name, List<Node> children)

2.10.     (int[] address, List<Node> children)

2.11.     (List<int> address, List<Node> children)

2.12.     (string name, string address, List<Node> children)

2.13.     (string name, int[] address, List<Node> children)

2.14.     (string name, List<int> address, List<Node> children)

 

3.       Делегаты

 

3.1.          string Titile(Node node)

 

summary

Возвращает подпись узла в псевдографическом изображении дерева. Аргумент ToString().

 

node

Ресурс подписи. Аргумент лямбда-выражения, передающегося в делегат.

 

returns

Подпись узла в псевдографическом изображении дерева.

 

4.       Методы

 

4.1.          Node Add(Node newChild)

 

summary

Добавляет новый узел в Children этого узла.

 

newChild

Узел, добавляемый в Children этого узла.

 

returns

Этот узел с новым узлом в Children.

 

4.2.          Node AddChildren(Node newChildren)

 

summary

Добавляет новые узлы в Children этого узла.

 

newChild

Узлы, добавляемые в Children этого узла.

 

returns

Этот узел с новыми узлами в Children.

 

4.3.          Node AddChildrenCopy(Node newChildren)

 

summary

Добавляет новые узлы в Children этого узла.

 

newChild

Узлы, копии которых добавляются в Children этого узла.

 

returns

Этот узел с новыми узлами в Children.

 

4.4.          Node AddCopy(Node newChild)

 

summary

Добавляет новый узел в Children этого узла.

 

newChild

Узел, копия которого добавляется в Children этого узла.

 

returns

Этот узел с новым узлом в Children.

 

4.5.          Node Copy()

 

summary

Возвращает копию этого узла.

 

returns

Копия этого узла.

 

4.6.          Node CorrectDescendants()

 

summary

Делает потомки этого узла правильными.

 

returns

Этот узел с правильными потомками.

 

4.7.          Node Find(int[] address)

 

summary

Возвращает узел с указанным Address из дерева, корнем которого является этот узел.

 

address

Address искомого узла.

 

returns

Искомый узел.

 

4.8.          Node Find(List<int> address)

 

summary

Возвращает узел с указанным Address из дерева, корнем которого является этот узел.

 

address

Address искомого узла.

 

returns

Искомый узел.

 

4.9.          List<Node> Find(bool isCorrect)

 

summary

Возвращает узлы с указанным IsCorrect из дерева, корнем которого является этот узел.

 

isCorrect

IsCorrect искомых узлов.

 

returns

Искомые узлы.

 

4.10.     List<Node> Find(string name)

 

summary

Возвращает узлы с указанным Name из дерева, корнем которого является этот узел.

 

name

Name искомых узлов.

 

returns

Искомые узлы.

 

4.11.     List<Node> Find(int number)

 

summary

Возвращает узлы с указанным Number из дерева, корнем которого является этот узел.

 

number

Number искомых узлов.

 

returns

Искомые узлы.

 

4.12.     int InnerLevelCount()

 

summary

Возвращает количество непустых уровней потомков этого узла. Потомки этого узла должны быть правильными.

 

returns

Количество непустых уровней потомков этого узла.

 

4.13.     int InnerLevelCount()

 

summary

Возвращает количество непустых уровней потомков этого узла. Потомки этого узла должны быть правильными.

 

returns

Количество непустых уровней потомков этого узла.

 

4.14.     int DescendantCount()

 

summary

Возвращает количество потомков этого узла.

 

returns

Количество потомков этого узла.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

5.       Примеры

5.1.          Создание подписи узла

5.2.          Address возвращает копию значения и принимает копию value

5.3.          Add добавляет ссылку на потомка

5.4.          Цепочка Add

5.5.          Add должен добавлять в дерево только новый узел

5.6.          Level

5.7.          IsValid

5.8.          MakeDescendantsValid

5.9.          Add задает правильные адреса добавляемым потомкам

5.10.     Copy

5.11.     AddCopy

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

Node Add(Node newChild)

 

Summary

Добавляет новый потомок на Level + 1 этого узла.

 

newChild

Добавляемый узел.

 

Returns

Этот узел с новым потомком на Level + 1 этого узла.

 

 

 

 

 

 

Node AddChildren(List<Node> newChildren)

 

Summary

Добавляет новые потомки на Level + 1 этого узла.

 

newChildren

Добавляемые узлы.

 

Returns

Этот узел с новыми потомками на Level + 1 этого узла.

 

 

Node AddChildrenCopy(List<Node> newChildren)

 

Summary

Добавляет новые потомки на Level + 1 этого узла.

 

newChildren

Узлы, копии которых добавляются на Level + 1 этого узла.

 

Returns

Этот узел с новыми потомками на Level + 1 этого узла.

 

 

 

 

Node AddCopy(Node newChild)

 

Summary

Добавляет новый потомок на Level + 1 этого узла.

 

newChild

Узел, копия которого добавляется на Level + 1 этого узла.

 

Returns

Этот узел с новым потомком на Level + 1 этого узла.

 

 

Node MakeDescendantsValid()

 

Summary

Устанавливает всем потомкам этого узла правильные адреса. Метода, делающего правильным у

 

Returns

Этот узел с правильными адресами потомков.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 
