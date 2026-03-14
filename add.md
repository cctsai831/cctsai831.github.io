# Quick Note II

``` graphviz
digraph {
    rankdir=LR;
    splines=false;
    {
        node [shape=circle];
        x1 [label=<x<sub>1</sub>>];
        x2 [label=<x<sub>2</sub>>];
        x3 [label=<x<sub>3</sub>>];
    }
    {
        rank=same;
        x1;
        x2;
        x3;
    }
    
    {
        node [shape=circle];
        a1 [label=<a<sub>1</sub><sup>(2)</sup>>];
        a2 [label=<a<sub>2</sub><sup>(2)</sup>>];
        a3 [label=<a<sub>3</sub><sup>(2)</sup>>];
        a4 [label=<a<sub>4</sub><sup>(2)</sup>>];
    }
    {
        rank=same;
        a1;
        a2;
        a3;
        a4;
    }
    
    {
        node [shape=circle];
        o1 [label=<y<sub>1</sub>>];
        o2 [label=<y<sub>2</sub>>];
    }
    {
        rank=same;
        o1;
        o2;
    }
    
    {x1;x2;x3} -> {a1, a2, a3, a4};
    {a1;a2;a3;a4} -> {o1, o2}
}
```
