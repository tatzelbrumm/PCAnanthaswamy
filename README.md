# Ananthaswamy Chapter 6  
# There's Magic in them Matrices  

### Example: EEG data to determine consciousness  

## linear maps in general  

A *linear map*  

$`f: \mathbb{R}^k\rightarrow\mathbb{R}^l`$  

$`\mathbb{R}^k\owns x\mapsto f(x)\in\mathbb{R}^l`$

with  

$`f(\kappa\,x+\lambda\,y)=\kappa\,f(x)+\lambda\,f(y)`$

is fully determined by the mapping of the basis vectors of $\mathbb{R}^k$ to the basis vectors of $\mathbb{R}^l$.

For finite $k$ and $l$, these mappings are conveniently arranged as matrix.  

### The linear map of the unit sphere is always an ellipsoid  

(sometimes a squished ellipsoid)
  
### Endormorphisms (represented by *square* matrices)  

are linear maps of a vector space onto itself

$`f: \mathbb{R}^k\rightarrow\mathbb{R}^l`$  

### Eigenvectors, eigenvalues

An endomorphism, fully defined by an $k\times k$ matrix, has $k$ eigenvalues $\lambda_i$, $`i\in\{1,\ldots,k\}`$.  
Each eigenvalue $\lambda_i$ has an eigenvector $\mathbf{x_i}$, 
such that $f(x_i)=\lambda_i x_i$.  
Due to the linearity of f, each eigenvector is determined up to a multiplicative factor $`\xi\neq 0`$,
i.e., if $`f(x_i)=\lambda_i x_i`$, then also $`f(\xi\,x_i)=\lambda_i\,\xi\,x_i`$.

Graphically, the mapping of an eigenvector is parallel to the eigenvector, scaled by the eigenvalue.  

Symmetric matrices have orthogonal eigenvectors.  
[Spektralsatz]

## Data series  

Data series of $N$ $k$-dimensional vectors $`\mathbf{x}^n\in\mathbb{R}^k`$ with $`n\in\{1,\ldots,N\}`$, in components $`x^n_i`$ with $`i\in\{1,\ldots,k\}`$. 

### Correlation

The **correlation matrix** of the data series is the sum of the **outer products** (multiply each component to each other component) of the data vectors,  
with elements  
$`\mathrm{corr}_{i\,j}=\sum_{n=1}^N x^n_i x^n_j`$ with $`i,j\in\{1,\ldots,k\}`$.

### Covariance  

If we're only interested in the correlation of the *change* of data points, we subtract the mean values  
$`\overline{x_i}={1\over N}\sum_{n=1}^N x^n_i`$  
from the data set before taking the outer product  
$`\mathrm{\sigma}_{i\,j}=\sum_{n=1}^N \left(x^n_i-\overline{x_i}\right) \left(x^n_j-\overline{x_i}\right)`$ with $`i,j\in\{1,\ldots,k\}`$.
