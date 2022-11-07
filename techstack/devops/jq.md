#gcp #kubernetes #k8s #cloud 

CLI tool for querying JSON

`jq [options…] filter [files]` is the basic format of `jq` command. As the most important and powerful parts of `jq`, basic filters and types are enough for 90% of the users.

The most common filters are,

-   `.key`
-   `.[]` (array)
-   `.[n]`, (Nth element of the array)
-   `.[n:m]`, (Nth to Mth elements of the array)
-   `A,B`, run two filters A and B with the same input
-   `A|B`, the output of A is the input of B
-   `(A)`, group operator

##### Links
- https://medium.com/geekculture/my-jq-cheatsheet-34054df5b650