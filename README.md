# MatrixTools

The Matrix2D library is a powerful toolset for working with 2D matrices. It provides a set of functions to perform common operations such as scaling, transforming, rotating, and multiplying matrices. This library is designed to be lightweight, efficient, and easy to integrate into your projects, making it a valuable asset for graphics programming, game development, and any application that involves 2D transformations.

The library is coded in C and uses the math library to perform the various subroutines.

M2d_print_mat(double a[3][3])
  prints matrix
  
M2d_copy_mat(double a[3][3],b[3][3])
  a = b
  
M2d_make_identity(double a[3][3])
  a = I
  
M2d_make_translation(double a[3][3], double dx, double dy)
  translates matrix a given deltaX, deltaY
  
M2d_make_scaling(double a[3][3], double sx , double sy)
  scales matrix a given scaleX, scaleY
  
M2d_make_rotation_cs(double a[3][3], double cs, double sn)
  rotates matrix a assuming cosine & sine are known
  
M2d_make_rotation(double a[3][3], double radians)
  rotates matrix a given radians
  
M2d_mat_mult(double res[3][3], double a[3][3], double b[3][3])
  multiplys 2 matrices res = a * b
  this is SAFE, i.e. the user can make a call such as 
  M2d_mat_mult(p,  p,q) or M2d_mat_mult(p, q, p) or  M2d_mat_mult(p, p, p)
  
M2d_mat_mult_pt(double p[2], double a[3][3], double q[2])
  mutliplies matrix by point p = a * q
  this is SAFE, i.e. the user may make a call like M2d_mat_mult_pt(p, a, p)
  
M2d_mat_mult_points(double X[], double Y[], double a[3][3], double x[], double y[], int numpoints)
  |X0 X1 X2 ...|       |x0 x1 x2 ...|
  |Y0 Y1 Y2 ...| = m * |y0 y1 y2 ...|
  | 1  1  1 ...|       | 1  1  1 ...|
  this is SAFE, i.e. the user may make a call like M2d_mat_mult_points(x,y, m, x,y, n)
