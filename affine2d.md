---
project:     affine2d
tagline:     2D affine transforms
---

## `local matrix = require'affine2d'`

--------------------------------------------------------------- --------------------------------------------------------------------------------------
`matrix(xx, yx, xy, yy, x0, y0) -> mt` <br> `matrix() -> mt`    Create a new matrix object. Defaults to identity matrix `1, 0, 0, 1, 0, 0`.
`mt:set(xx, yx, xy, yy, x0, y0) -> mt`                          Set the matrix fields.
`mt:reset() -> mt`                                              Set the matrix to the identity matrix `1, 0, 0, 1, 0, 0`.
`mt:unpack() -> xx, yx, xy, yy, x0, y0`                         Unpack the matrix fields.
`mt:copy() -> newmt`                                            Create a new matrix object with the same fields as `mt`.
`mt:transform_point(x, y) -> tx, ty` <br> `mt(x, y) -> tx, ty`  Transform a 2D point.
`mt:transform_distance(x, y) -> dx, dy`                         Transform a point ignoring translation.
`mt:multiply(bxx, byx, bxy, byy, bx0, by0) -> mt`               Multiply `mt * b` and store the result in `mt`.
`mt:transform(bxx, byx, bxy, byy, bx0, by0) -> mt`              Multiply `b * mt` and store the result in `mt`.
`mt:determinant() -> det`                                       Compute the matrix determinant.
`mt:is_invertible() -> true | false`                            Check if the matrix is invertible, that is, if the determinant is not 0, 1/0 or -1/0.
`mt:scalar_multilpy(s) -> mt`                                   Mulitply each field of the matrix with a scalar value.
`mt:inverse() -> newmt`                                         Return the inverse matrix, or nothing if the matrix is not invertible.
`mt:translate(x, y) -> mt`                                      Translate the matrix.
`mt:scale(sx, sy) -> mt` <br> `mt:scale(s)`                     Scale the matrix.
`mt:rotate(angle) -> mt`                                        Rotate the matrix. The angle is in degrees.
`mt:skew(angle_x, angle_y) -> mt`                               Skew the matrix. Angles are in degrees.
`mt:is_identity() -> true | false`                              Check if the matrix is the identity matrix, thus having no effect on the input.
`mt:has_unity_scale() -> true | false`                          Check that no scaling is done with this transform, only flipping and multiple-of-90-degree rotation.
`mt:has_uniform_scale() -> true | false`                        Check that scaling with this transform is uniform on both axes.
`mt:scale_factor() -> s`                                        Largest dimension of the bounding box of the transformed unit square.
`mt:is_pixel_exact() -> true | false`                           Check that pixels map 1:1 with this transform so that no filtering is necessary to project an image to the screen for example.
`mt:is_straight() -> true | false`                              Check that there's no skew and that there's no rotation other than multiple-of-90-degree rotation.
`mt1 * mt2 -> newmt`                                            Multiply two matrices and return the result as a new matrix.
`mt1 == mt2`                                                    Test two matrices for equality. Matrices are considered equal when their fields are equal.
--------------------------------------------------------------- --------------------------------------------------------------------------------------

