# Graph

A (hopefully) simple demonstration of [neo4j](https://neo4j.com/) using the [Movie Database](http://example-data.neo4j.org/3.0-datasets/cineasts.tgz) example dataset.

This dataset includes nodes with the following labels:

* Actor
* Director
* Movie
* Person

## Useful Links

[Cypher Refcard](https://neo4j.com/docs/cypher-refcard/current/)
[Cypher tutorial](http://neo4j.com/docs/developer-manual/current/cypher/#query-match)

## Useful cypher snippets

  1. Return all distinct labels:

    ```cypher
    MATCH (n)
    WITH DISTINCT labels(n) AS labels
    UNWIND labels AS label
    RETURN DISTINCT label
    ORDER BY label;
    ```

  2. Return all distinct relationships:

    ```cypher
    MATCH (n)-[r]-(m)
    RETURN DISTINCT type(r) as relationship
    ORDER BY relationship;
    ```

## Installation

If [available in Hex](https://hex.pm/docs/publish), the package can be installed as:

  1. Add `graph` to your list of dependencies in `mix.exs`:

    ```elixir
    def deps do
      [{:graph, "~> 0.1.0"}]
    end
    ```

  2. Ensure `graph` is started before your application:

    ```elixir
    def application do
      [applications: [:graph]]
    end
    ```
