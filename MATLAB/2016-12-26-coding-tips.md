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
