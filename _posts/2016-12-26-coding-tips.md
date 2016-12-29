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
Usage: first tranform the big ``mat`` file into MAT-file, use ``matObj = matfile('myBigData.mat');``
