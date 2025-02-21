Data challenge 1 for 3x2pt

Contains:
- Covariance matrx (2055x2055)
- Data vector (2055)

Relevant general details:
8 tomographic bins
theta_min = 2.5, theta_max = 250., ntheta=15

Covariance matrix details:
For ggl, exclude bin combos where the z_min(lens bin) > z_max(source bin), i.e. where lens is fully behind source. This results in the exclusion of bin combos (l,s) = [(5,0),(6,0),(6,1),(7,0),(7,1),(7,2),(7,3)]. These have already been excluded in the provided matrix and data vector.

The matrix, as is, is not positive definite. To make the matrix positive definite, you must remove the first two theta bins from each section of the galaxy-galaxy lensing and galaxy-clustering components. This corresponds roughly to a galaxy clustering cutoff of 1.5 Mpc/h. (Using the actual 1.5Mpc/h cut will lead to the removal of a few additional theta bins cut at low redshift.)
