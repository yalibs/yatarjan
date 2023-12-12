# yatarjan
Yet another framework-agnostic tarjan scc detection algorithm implementation for Java applications

See [the paper](https://sites.cs.ucsb.edu/~gilbert/cs240a/Old/cs240aSpr2011/slides/TarjanDFS.pdf) for detailed info about the algorithm.

## Usage

```java
public class Main {
    public static void main(String[] args) {
        // Triangle circular graph in the form of a vertex-edge mapping
        var graph = new HashMap<String,List<String>>();
        graph.put("a", List.of("b", "c")); // vertex "a" is connected to "b" and "c"
        graph.put("b", List.of("c")); // vertex "b" is connected to "c"
        graph.put("c", List.of("a")); // vertex "c" is connected to "a"
        var sccs = Tarjan.getStronglyConnectedComponents(graph);
        // sccs = [[a,b,c]]
    }
}
```
