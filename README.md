# Variance-reduction-via-gradient-sketching
Here you can find the implementation of [this paper](https://arxiv.org/pdf/1809.03054.pdf) for the course of optimization methods in machine learning.\

This github containt the following documents:
- Report_1.pdf - The document that describes method, why to use this method, and where to use this method
- SEGA_presentation.pptx - The presentation about the method that explains how it works
- SEGA.ipynb - The Jupyter notebook that runs some experiments on SEGA. This document is designed as the educational notebook with comments.

If you wish to learn about method, feel free to download SEGA.ipynb, read it, run it, and change it.\
You can also access this notebook in colab using [this link](https://colab.research.google.com/drive/1TA99viKEpGh0p252v7RePmJ7_MxDoM16#scrollTo=wq-ASEPIU7XJ)

# Short description
The SEGA method is used for optimization of the following regularized empirical risk problems.\
![](/images/emp_risk.png)\
The algorithm is the following\
![](/images/algo.png)\
Here, we use global biased estimation h of the gradient to build and unbiased estimation g, that we can use further in during gradient step. Description of variables and convergence you can see in the original paper or presentation.\

This method has the beautiful property: it is variance reduced. Here you can see why\
Since we have some changing system with some states, it is natural for lyapunov function to appear, and this lyapunov function can be used to estimate current state. lyapunov function for SEGA is the following:\
![](/images/lyapunov.png)\
Authors of the paper state that under some assumptions and conditions, this function has iterates linear convergence. Decreasing in this function means that both x and gradient converge to the optimum. And since gradient converges to the gradient at optimum, the method is variance-reduced.\
