---
layout: post
title: "Coding tips"
date: 2016-12-26
---

saving and loading  MATLAB structure  

* define data structure ``mystruct = struct('fieldName1',[],'fieldName2',[],...)``, setting the values of each field: ``mystruct.fieldName1 = variable1``.  

* save struct preserve individual variables ``save(saveFileName, '-struct','mystruct')``  

* run matlab in command line or Linux cluster. Use ``varargin`` to pass parameters, use ``matlab -r "myscript(2)"`` to run matlab script.

* enable parallel computing. MATLAB has several parallel computing tool boxes enable you to use the multiple cores to accelerate your code. The simplest way is at the beginning of script, inserting
``matlabpool numberofpool`` (after MATLAB 2013b，it is replaced by ``parpool``), at the end of script add ``matlabpool colse``

* _Handle large matrix_ After MATLAB 2011b, you can use ``MAT-file`` to save and load part of a ``.mat`` file which accelerate speed when you are running out of memory. The official document can be found [here](http://blogs.mathworks.com/loren/2011/10/14/new-mat-file-functionality-in-r2011b/).  
Usage: first tranform the big ``mat`` file into MAT-file, use ``matObj = matfile('myBigData.mat')``. But inorder to use this fucnction the save ``mat`` file has to be version 7.3 format, use ``save('myfile.mat','variables','-v7.3')``.

* ``eval `` This is a very useful function especially when you want to evaluate a certain commond or phrases in a loop or in a string vector. ``feval`` is the corresponding function for function handles.

* Advanced programming techniques can be found [here](https://math.la.asu.edu/files/support/docs/matlab_workshop/Adv_Programming.pdf) and [here](http://www2.engr.arizona.edu/~sail/matlab_optimization.pdf). Tips on writing MATLAB [function](http://uk.mathworks.com/matlabcentral/mlc-downloads/downloads/submissions/21653/versions/3/previews/tutorial/writingFunctions.html). A stratege to overcome the downside of _varargin_ is to specify the name of each parameters, by doing so you don't need to worry about the orer of different arguments. For example : `function myfunc(varargin)
   [A,B,C,D,E] = process_options(varargin,'A',3,'B',1,'C',2,'D',5,'E',9)`; A tutorial of [debuging and optimization](http://www2.engr.arizona.edu/~sail/matlab_optimization.pdf).
