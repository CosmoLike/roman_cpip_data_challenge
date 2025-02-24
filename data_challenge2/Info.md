# Details

- Covariance matrix (2055x2055)
- Data vector (2055)

Covariance matrix details:
For ggl, exclude bin combos where the z_min(lens bin) > z_max(source bin), i.e. where lens is fully behind source. This results in the exclusion of bin combos (l,s) = [(5,0),(6,0),(6,1),(7,0),(7,1),(7,2),(7,3)]. These have already been excluded in the provided matrix and data vector.

The matrix is positive definite as given.
