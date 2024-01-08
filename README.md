# principal_coordinates_1

### Multidimensional Scaling Analysis with the `eurodist` Dataset

This script performs classical multidimensional scaling (MDS) on the `eurodist` dataset using R's `stats` package. The aim is to visualize the distances among major European cities in a two-dimensional space.

1. **Loading the `stats` Package**:
   ```R
   library(stats)

eurodist
datos = eurodist

Xfull = cmdscale(datos, k = 20, eig = TRUE, add = FALSE, x.ret = FALSE)

X = cmdscale(datos, k = 2, eig = TRUE, add = FALSE, x.ret = FALSE)
X

require(graphics)
x = X$points[,1]
y = X$points[,2]
plot(x, -y, type="n", xlab="", ylab="", main="cmdscale(eurodist)")
text(x, -y, rownames(X$points), cex=0.8)


