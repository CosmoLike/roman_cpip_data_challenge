# Roman Fourier space 3x2pt analysis

## Relevant general details

- 8 tomography bins
- Logarithmic Fourier ell bins: ell_min = 30, ell_max = 4000, Ncl=15
- Covariance matrix (1485x1485)
- Data vector (1485)

## Data vector format

Each data vector contains two columns:

- column 0: index i;
- column 1: value of data vector for corresponding probe/bin combination

The data vectors are ordered with the first block corresponding to E-mode cosmic shear power spectrum C_EE(ell), followed by galaxy-galaxy lensing power spectrum C_gl(ell), and galaxy clustering power spectrum C_gg(ell)

## Covariance format

- column 0, 1: matrix indices
- column 2, 3: the corresponding bin-averaged angular separations (in radians) of the element
- column 4, 5, 6, 7: the tomographic bins involved
- column 8, 9: the Gaussian part and the non-Gaussian part of the element. The total value is the sum of the two.

## Covariance matrix details:

For ggl, exclude bin combos where the z_min(lens bin) > z_max(source bin), i.e. where lens is fully behind source. This results in the exclusion of bin combos (l,s) = [(4,0),(5,0),(6,0),(6,1),(6,2),(7,0),(7,1),(7,2),(7,3)]. These have already been excluded in the provided matrix and data vector.

The matrix, as is, is not positive definite. To make the matrix positive definite, you must remove the last two ell bins from each section of the galaxy-galaxy lensing and galaxy-clustering components (see challenge3.defaultmask)

