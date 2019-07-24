# Laplace-Smoothing-Animation
Jupyter notebook tag-a-long to Medium blog "Laplace Smoothing and the Sunrise Problem"

The Medium blog is [here](https://medium.com/p/1ac6a22449b9/edit). 

The notebook creates a visualization of how the Laplace smoothing probabilities change with <a href="https://www.codecogs.com/eqnedit.php?latex=$\alpha$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\alpha$" title="$\alpha$" /></a>. 

Hopefully the visualization shows why we say Laplace smoothing adjusts our probabilities towards a uniform distribution.
But, for those who prefer math...

Let <a href="https://www.codecogs.com/eqnedit.php?latex=$d$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$d$" title="$d$" /></a> be a positive integer. 
For <a href="https://www.codecogs.com/eqnedit.php?latex=$i=1,\ldots,d$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$i=1,\ldots,d$" title="$i=1,\ldots,d$" /></a>, let

<a href="https://www.codecogs.com/eqnedit.php?latex=$$\theta_i&space;=&space;\frac{x_i&space;&plus;&space;\alpha}{N&space;&plus;&space;d},$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$\theta_i&space;=&space;\frac{x_i&space;&plus;&space;\alpha}{N&space;&plus;&space;d},$$" title="$$\theta_i = \frac{x_i + \alpha}{N + d},$$" /></a>

where <a href="https://www.codecogs.com/eqnedit.php?latex=$x_i$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$x_i$" title="$x_i$" /></a> is a positive integer (the number of observations of an event), <a href="https://www.codecogs.com/eqnedit.php?latex=$N$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$N$" title="$N$" /></a> is a positive integer greater than <a href="https://www.codecogs.com/eqnedit.php?latex=$x_i$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$x_i$" title="$x_i$" /></a> for <a href="https://www.codecogs.com/eqnedit.php?latex=$i=1,\ldots,d$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$i=1,\ldots,d$" title="$i=1,\ldots,d$" /></a> (the total number of occasions to observe an event), and <a href="https://www.codecogs.com/eqnedit.php?latex=$\alpha$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\alpha$" title="$\alpha$" /></a> is a non-negative real number (the pseudo-count). 

We would like to show 
1. if <a href="https://www.codecogs.com/eqnedit.php?latex=$\theta_i&space;\geq&space;1/d$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\theta_i&space;\geq&space;1/d$" title="$\theta_i \geq 1/d$" /></a>, then <a href="https://www.codecogs.com/eqnedit.php?latex=$\theta_i&space;\leq&space;x_i/N$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\theta_i&space;\leq&space;x_i/N$" title="$\theta_i \leq x_i/N$" /></a>, and
2. if <a href="https://www.codecogs.com/eqnedit.php?latex=$\theta_i&space;\leq&space;1/d$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\theta_i&space;\leq&space;1/d$" title="$\theta_i \leq 1/d$" /></a>, then <a href="https://www.codecogs.com/eqnedit.php?latex=$\theta_i&space;\geq&space;x_i/N$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\theta_i&space;\geq&space;x_i/N$" title="$\theta_i \geq x_i/N$" /></a>.

If <a href="https://www.codecogs.com/eqnedit.php?latex=$\alpha=0$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\alpha=0$" title="$\alpha=0$" /></a>, then both inequalities hold. 

Suppose <a href="https://www.codecogs.com/eqnedit.php?latex=$\theta_i&space;\geq&space;1/d$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\theta_i&space;\geq&space;1/d$" title="$\theta_i \geq 1/d$" /></a> and <a href="https://www.codecogs.com/eqnedit.php?latex=$\alpha&space;>&space;0$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\alpha&space;>&space;0$" title="$\alpha > 0$" /></a>. 
Then

<a href="https://www.codecogs.com/eqnedit.php?latex=$\begin{align*}&space;\frac{1}{d}&space;&&space;\leq&space;\frac{x_i&space;&plus;&space;\alpha}{N&plus;\alpha&space;d},&space;\\&space;N&plus;\alpha&space;d&space;&&space;\leq&space;x_i&space;d&space;&plus;&space;\alpha&space;d,&space;\\&space;N&space;&&space;\leq&space;x_i&space;d,&space;\\&space;N&space;\alpha&space;&&space;\leq&space;\alpha&space;x_i&space;d,&space;\\&space;N&space;x_i&space;&plus;&space;N&space;\alpha&space;&&space;\leq&space;N&space;x_i&space;&plus;&space;\alpha&space;x_i&space;d,&space;\\&space;\frac{x_i&space;&plus;&space;\alpha}{N&space;&plus;&space;\alpha&space;d}&space;&\leq&space;\frac{x_i}{N}.&space;\end{align*}$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\begin{align*}&space;\frac{1}{d}&space;&&space;\leq&space;\frac{x_i&space;&plus;&space;\alpha}{N&plus;\alpha&space;d},&space;\\&space;N&plus;\alpha&space;d&space;&&space;\leq&space;x_i&space;d&space;&plus;&space;\alpha&space;d,&space;\\&space;N&space;&&space;\leq&space;x_i&space;d,&space;\\&space;N&space;\alpha&space;&&space;\leq&space;\alpha&space;x_i&space;d,&space;\\&space;N&space;x_i&space;&plus;&space;N&space;\alpha&space;&&space;\leq&space;N&space;x_i&space;&plus;&space;\alpha&space;x_i&space;d,&space;\\&space;\frac{x_i&space;&plus;&space;\alpha}{N&space;&plus;&space;\alpha&space;d}&space;&\leq&space;\frac{x_i}{N}.&space;\end{align*}$" title="$\begin{align*} \frac{1}{d} & \leq \frac{x_i + \alpha}{N+\alpha d}, \\ N+\alpha d & \leq x_i d + \alpha d, \\ N & \leq x_i d, \\ N \alpha & \leq \alpha x_i d, \\ N x_i + N \alpha & \leq N x_i + \alpha x_i d, \\ \frac{x_i + \alpha}{N + \alpha d} &\leq \frac{x_i}{N}. \end{align*}$" /></a>

The proof of 2. follows similarly to the proof of 1. by switching the inequality.
