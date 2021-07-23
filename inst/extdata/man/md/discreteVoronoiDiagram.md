discreteVoronoiDiagram
======================

Usage
-----

    discreteVoronoiDiagram(X)

| Argument | Description              |
| -------: | :----------------------- |
|        X | A `matrix` (see Details) |

Details
-------

The `discreteVoronoiDiagram` function is designed for a `numeric` `matrix` argument.
Each row represents a "target."
Each column represents a "source."
Each element represents the proximity of the corresponding source and target
(should be nonnegative), and
does not necessarliy have to be the
[Euclidean distance](https://en.wikipedia.org/wiki/Euclidean_distance).

Value
-----

An `integer` `matrix` with the same number of rows as `X`.

Each row contains the indices for the sources which are nearest
the target of that row.

The number of columns will equal the number of sources
associated with the target having the greatest number of
nearest sources. See Examples.

Examples
--------

    X <- matrix(nrow = 3, c(4, 3, 8, 9, 5, 1, 2, 7, 1))
    > rownames(X) <- c("target.1", "target.2", "target.3")
    > colnames(X) <- c("source.1", "source.2", "source.3")
    > X
    #          source.1 source.2 source.3
    # target.1        4        9        2
    # target.2        3        5        7
    # target.3        8        1        1
    > discreteVoronoiDiagram(X)
    #      [,1] [,2]
    # [1,]    3   NA
    # [2,]    1   NA
    # [3,]    2    3
