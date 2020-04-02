# Druid
### For working with trees and creating a pseudo-graphic image of a tree.
------------
### Example
```csharp
Node myTree = new Node("My tree")
    .Add(new Node("a")
        .Add(new Node("b"))
        .Add(new Node("c")
            .Add(new Node("d")))
        .Add(new Node("e")))
    .Add(new Node("f")
        .Add(new Node("g"))
        .Add(new Node("h")))
    .Add(new Node("i"));

Console.WriteLine(tree.ToString(x => $"({x.AddressAsString}) {x.Name}"))

//■ (0) My tree
//├─■ (0,0) a
//│ ├─■ (0,0,0) b
//│ ├─■ (0,0,1) c
//│ │ └─■ (0,0,1,0) d
//│ └─■ (0,0,2) e
//├─■ (0,1) f
//│ ├─■ (0,1,0) g
//│ └─■ (0,1,1) h
//└─■ (0,2) i
```
***
## Benefits

1. The position of the node in the tree is determined by only one parameter: `List<int> Address { get; set; }`. The child Address contains the Address of its parent.

##### 2. A table containing a tree of such nodes cannot be written more than one root.
Typically, a node in a tree is defined by two parameters: `Id` and `ParentId`. For the root `ParentId == null`, therefore, the column "ParentId" must be set with the `NULL` property. But `null! = null`, so there may be several roots in the table. If the node is not a root, then its Address contains the Address of its parent, so the "ParentId" column is not required.
##### 3. The Node class plays the role of a base class for your specific classes and contains all the necessary properties (the numbers of nodes, their generations in the tree, etc.) and methods (Add, Search, Sort, Save, Load, etc.), therefore it is simple and powerful.
##### 4. The ToString method returns a pseudo-graphic drawing of a tree. This is very convenient for quick work with trees in a console application. To see the tree, just use `Console.WriteLine (<Node>)`.



