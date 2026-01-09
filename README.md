# Ananthaswamy Chapter 6: There's Magic in them Matrices  

### A General Remark  

So far (in the first 7 chapters of "Why Machines Learn"), 
Ananthaswamy presents historic building blocks (algorithms, methods) that evolved into the foundation of contemporary machine learning ("Artificial Intelligence").  
As presented, the building blocks are *very* basic, often oversimplified by today's state of the art,
and not (yet) very related to each other.  
This makes ontologies without playing with the concepts presented a fool's errand.

## A New Item in the Toolbox: Principal Component Analysis (PCA)  

For a data set in which each datum is described as a vector of different properties,  
the Principal Component Analysis is a method to *rotate* (i.e., transform its components such that lengths and angles are preserved) the coordinates of all the data vectors 
such that the *fewest* number of coordinates explain *most* of the **variance** (distance from the arithmetic mean squared) of the data points.

### Example: EEG data to determine consciousness  

## Linear Maps in general  

A *linear map*  

$`f: \mathbb{R}^k\rightarrow\mathbb{R}^l`$  

$`\mathbb{R}^k\owns x\mapsto f(x)\in\mathbb{R}^l`$

with  

$`f(\kappa\,x+\lambda\,y)=\kappa\,f(x)+\lambda\,f(y)`$

is fully determined by the mapping of the basis vectors of $\mathbb{R}^k$ to the basis vectors of $\mathbb{R}^l$.

For finite $k$ and $l$, these mappings are conveniently arranged as matrix.  

### The linear map of the unit sphere is always an ellipsoid  

[(sometimes a squished ellipsoid)](https://chatgpt.com/share/696006b6-fb58-8000-bb3f-67e101261339)  
  
### Endormorphisms (represented by *square* matrices)  

are linear maps of a vector space onto itself

$`f: \mathbb{R}^k\rightarrow\mathbb{R}^l`$  

### Eigenvectors, eigenvalues

An endomorphism, fully defined by an $k\times k$ matrix, has $k$ eigenvalues $\lambda_i$ with $`i\in\{1,\ldots,k\}`$.  
Each eigenvalue $\lambda_i$ has an eigenvector $\mathbf{x_i}$, 
such that $f(x_i)=\lambda_i x_i$.  
Due to the linearity of f, each eigenvector is determined up to a multiplicative factor $`\xi\neq 0`$,
i.e., if $`f(x_i)=\lambda_i x_i`$, then also $`f(\xi\,x_i)=\lambda_i\,\xi\,x_i`$.

Graphically, the mapping of an eigenvector is parallel to the eigenvector, scaled by the eigenvalue.  

Symmetric matrices have orthogonal eigenvectors.  
[Spektralsatz](https://chatgpt.com/share/69600700-7840-8000-839e-733ebd41c745)  

## Data series  

Data series of $N$ $k$-dimensional vectors $`\mathbf{x}^n\in\mathbb{R}^k`$ with $`n\in\{1,\ldots,N\}`$, in components $`x^n_i`$ with $`i\in\{1,\ldots,k\}`$. 

### Correlation

The **correlation matrix** of the data series is the sum of the **outer products** (multiply each component to each other component) of the data vectors,  
with elements  
$`\mathrm{corr}_{i\,j}=\sum_{n=1}^N x^n_i x^n_j`$ with $`i,j\in\{1,\ldots,k\}`$.  

By construction, the matrix is symmetric: $`\mathrm{corr}_{i\,j}=\mathrm{corr}_{j\,i}`$.

### Covariance  

If we're only interested in the correlation of the *change* of data points, we subtract the mean values  
$`\overline{x_i}={1\over N}\sum_{n=1}^N x^n_i`$  
from the data set before taking the outer product  
$`\sigma_{i\,j}=\sum_{n=1}^N \left(x^n_i-\overline{x_i}\right) \left(x^n_j-\overline{x_i}\right)`$ with $`i,j\in\{1,\ldots,k\}`$.  

It may be simpler to calculate  
$`\sum_{n=1}^N x^n_i\,x^n_j-N\,\overline{x_i}\,\overline{x_j}=
\sum_{n=1}^N \left(x^n_i-\overline{x_i}\right) \left(x^n_j-\overline{x_i}\right)`$

By construction, $`\mathbb{\sigma}`$ is symmetric: $`\sigma_{i\,j}=\sigma_{j\,i}`$

## Related LLM chats

* [Linear mapping and ellipsoids](https://chatgpt.com/share/696006b6-fb58-8000-bb3f-67e101261339)  
    Beweise: Jede lineare Abbildung bildet die Einheitskugel auf ein Ellipsoid ab  
    Antwort: Im Prinzip ja, aber manchmal wird das Ellipsoid in einigen Dimensionen geplättet. Dann wird aus der Randfläche ein durchgehendes Volumen.
* [Spektralsatz Beweis Lineare Algebra](https://chatgpt.com/share/69600700-7840-8000-839e-733ebd41c745)  
    Einfacher (für Haltungsjournalisten) aber trotzdem mathematisch sauberer und sauber notierter Beweis des Spektralsatzes in der Linearen Algebra, mit Veranschaulichung.
* [Stabile Rotationen Starrkörper](https://chatgpt.com/share/6960eea9-2ec8-8000-8601-48cc7c9b7743)   
    * [Axial rotierender Fisch](./fish_stable_I1.gif)    
    * [Horizontal rotierender Fisch](./fish_stable_I3.gif)    
    * [Vertikal taumelnder Fisch](./fish_intermediate_axis_instability.gif)    
    * [Vertikal rotierender Fisch](https://www.youtube.com/watch?v=-mJENuEN_rs&t=87s)  
* [Mahalanobis-Abstand einfach erklärt](https://chatgpt.com/share/6960c0fa-ebec-8000-a507-26eba5d772db)  
    Einfache Erklärung mit Beispiel(en) für [Mahalanobis-Abstand](http://www.statistics4u.info/fundstat_germ/ee_mahalanobis_distance.html), für Haltungsjournalisten  
    ... weil's [der X-"Nazi" Lars dem Weisbrod gegenüber erwähnt hat](https://x.com/hortarimar/status/2007452454930035113). 
* [Whitening and Mahalanobis Distance](https://chatgpt.com/share/6960271f-a790-8000-a76c-0237aa0f4f24)  
    "Whitening", also das Zurechtstauchen des Hauptkomponenten-Ellipsoids in eine Kugel, transformiert den Mahalanobis-Abstand in einfachen euklidischen Abstand.
