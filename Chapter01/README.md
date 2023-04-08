# Chapter 1
## Tensors and Linear Algebra
```cpp
// LIBRARIES
#include <Eigen/Dense>              // lib for dense matrix operations
#include <Eigen/SparseCore>         // lib for (most) sparse matrix operations

// BASIC TYPES
Matrix<double, 2, 2> m;             // fixed size 2x2 matrix
Matrix<double, Dynamic, 2> m;       // dynamic rows, fixed cols
Matrix<double, Dynamic, Dynamic> m; // dynamic rows, dynamic cols (initializes as 3x3)
Matrix<double, 3, 3, RowMajor> m;   // Specify row major ordering (defaults to column major)

// TYPE ALIASES
Matrix3f m;                         // alias for Matrix<float, 3, 3>
Vector3i v;                         // alias for Matrix<int, 3, 1>
RowVector3f rv;                     // alias for Matrix<float, 1, 3>
MatrixXf m;                         // alias for Matrix<float, Dynamic, Dynamic> 
VectorXf v;                         // alias for Matrix<float, 1, Dynamic>

// INITIALIZATIONS
Matrix2f m {                        // initialize fixed size matrix w/ values
    {1, 2},
    {4, 5}
};
MatrixXf m(10,15);                  // initialize dynamic matrix w/ size 10x15
VectorXf v(10);                     // initialize dynamic vector w/ size 10

```