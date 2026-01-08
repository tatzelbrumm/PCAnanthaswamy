# Ananthaswamy Chapter 6  
# There's Magic in them Matrices  

### Example: EEG data to determine consciousness  

## linear maps in general  

A *linear map*  

$$f: \mathbb{R}^k\rightarrow\mathbb{R}^l$$  

$$\mathbb{R}^k\owns x\mapsto f(x)\in\mathbb{R}^l$$

with  

$$f(\kappa x+\lambda y)=\kappa f(x)+\lambda f(y)$$

is fully determined by the mapping of the basis vectors of $\mathbb{R}^k$ to the basis vectors of $\mathbb{R}^l$.
  
### endormorphisms (represented by *square* matrices)  

An $k\times k$ matrix has $k$ eigenvalues $\lambda_i$, $i\in\{1\ldots k\}$.  
Each eigenvalue $\lambda_i$ has an eigenvector $\mathbf{x_i}$, 
such that $f(x_i)=\lambda_i f(x_i)$.

Symmetric matrices have orthogonal eigenvectors.  

## Data series  

Data series of $N$ $k$-dimensional vectors.  

