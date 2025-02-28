# Details

- Covariance matrix (2010x2010)
- Data vector (2010)

Covariance matrix details:
For ggl, exclude bin combos where the z_min(lens bin) > z_max(source bin), i.e. where lens is fully behind source. This results in the exclusion of bin combos (l,s) = [(4,0),(5,0),(5,1),(6,0),(6,1),(6,2),(7,0),(7,1),(7,2),(7,3)]. These have already been excluded in the provided matrix and data vector.

The matrix, as is, is not positive definite. To make the matrix positive definite, you must remove the first two theta bins from each section of the galaxy-galaxy lensing and galaxy-clustering components. This corresponds roughly to a galaxy clustering cutoff of 1.5 Mpc/h. (Using the actual 1.5Mpc/h cut will lead to the removal of a few additional theta bins cut at low redshift.)
