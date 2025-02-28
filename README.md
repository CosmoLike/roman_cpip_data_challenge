# Data challenge for 3x2pt (Real Space)

## Each Directory Contains:
- Covariance matrix
- Redshift distribution
- Data vector
- Additional information on specific scenario

## Relevant general details:
  - 8 tomographic bins
  - theta_min = 2.5, theta_max = 250., ntheta=15

## Data vector format

Each data vector contains two columns:
  - column 0: index i;
  - column 1: value of data vector for corresponding probe/bin combination

The data vectors are ordered with the first block corresponding to xi+, followed by xi-, gammat, w

Within each probe block, the first data point corresponds to the lowest theta bin in the first redshift combination, proceeding through all theta bins before moving to the next bin combination.

The full ordering can be found within the fully indexed matrix, which follows the format of the [CosmoCov](https://github.com/CosmoLike/CosmoCov/tree/master) output files. 
 - column 0, 1: matrix indices
 - column 2, 3: the corresponding bin-averaged angular separations (in radians) of the element
 - column 4, 5, 6, 7: the tomographic bins involved
 - column 8, 9: the Gaussian part and the non-Gaussian part of the element. The total value is the sum of the two.

For galaxy-galaxy lensing, bin combinations where z_min(lens bin) > z_max(source bin), i.e. where lens is fully behind source, have been excluded from both the data vector and the covariance matrix. Details on which bin combinations this impacts can be found within the directory for that example.
