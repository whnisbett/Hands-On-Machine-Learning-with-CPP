# Chapter 1: Eigen
```cpp
// LIBRARIES
#include <Eigen/Dense>                         // lib for dense matrix operations
#include <Eigen/SparseCore>                    // lib for (most) sparse matrix operations

// BASIC TYPES
Matrix<double, 2, 2> m;                        // fixed size 2x2 matrix
Matrix<double, Dynamic, 2> m;                  // dynamic rows, fixed cols
Matrix<double, Dynamic, Dynamic> m;            // dynamic rows, dynamic cols (initializes as 3x3)
Matrix<double, 3, 3, RowMajor> m;              // Specify row major ordering (defaults to column major)

// TYPE ALIASES
Matrix3f m;                                    // alias for Matrix<float, 3, 3>
Vector3i v;                                    // alias for Matrix<int, 3, 1>
RowVector3f rv;                                // alias for Matrix<float, 1, 3>
MatrixXf m;                                    // alias for Matrix<float, Dynamic, Dynamic> 
VectorXf v;                                    // alias for Matrix<float, 1, Dynamic>

// INITIALIZATIONS
Matrix2f m {                                   // initialize fixed size matrix w/ values
    {1, 2},
    {4, 5}
};
MatrixXf m(10,15);                             // initialize dynamic matrix w/ size 10x15
VectorXf v(10);                                // initialize dynamic vector w/ size 10

// EIGEN::MAP
int data[] = {1, 2, 3, 4};                     // initialize array
Eigen::Map<Eigen::RowVectorxi> v(data,4);      // create RowVector that points to that data and some new values

std::vector<float> data = {1,2,3,4,5,6,7,8,9}; // same process but for std::vectors
Eigen::Map<Eigen::MyMatrix33f> a(data.data());

// BASIC MATHEMATICAL OPERATIONS
using namespace Eigen;
auto a = Matrix2d::Random();
auto b = Matrix2d::Random();

auto result = a + b;                           // addition of 2 matrices
a += b;                                        // add b to a and update a
result = a.array() * b.array();                // element wise multiplication result = a.array() / b.array();
result = a * b;                                // matrix multiplication
a = b.array() * 4;                             // scalar multiplation = b.array() * scalar


// ACCESSORS
Eigen::Matrixxf m(4,4);
Eigen::Matrix2f b = m.block(1,1,2,2);          // copy middle part 2x2 submatrix
m.row(1).array() += 3;                         // access and update row 1
m.col(2).array() /= 4;                         // access and update col 2

Eigen::Vectorxf v(2);
m.colwise() += v;                              // broadcast operations across each column (use .rowwise() for rows)
```