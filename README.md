# diagrams
testing different diagram rendering diagrams in markdown


graph TD;
    A --> B;
    B --> C;
    C --> A;


```dot
digraph G {
    A -> B;
    B -> C;
    C -> A;
}


```ditaa
+--------+   +-------+    +-------+
|        | --+ Ditaa +--> |       |
|  Text  |   +-------+    |  PNG  |
|Document|   |!magic!|    | Image |
|     {d}|   |       |    |       |
+---+----+   +-------+    +-------+
    :                         ^
    |       Lots of work      |
    +-------------------------+
