---
layout: post
title:  How to use treeomics
date: 2017-06-11
desc:  How to use treeomics
keywords: "blog"
categories: 
tags: 
icon: icon-html
---

# How to use treeomics

Follow the instruction: https://github.com/johannesreiter/treeomics install python, then install pip: 
    
    
    wget https://bootstrap.pypa.io/get-pip.py
    
    
    python3.4 get-pip.py
    
    
    python3.4 -m pip install numpy==verision

Then use pip to install all required python packages Then install IBM ILOG CPLEX Optimization Studio with academic license. Configure the python API. Add path: export PYTHONPATH=yourCplexhome/python/VERSION/PLATFORM.   (I'm using Cplex 1.7 with Python3.5, python3.4 is not compatible with Cplex1.7)   **You might need this to overwrite the default common vars file:** \--common_vars_file input/ExAC/ExAC_sites_0_001.csv **You might need other perl modules for Cicurs, install locally and: ** For local install: perl -MCPAN -Mlocal::lib -e shell (edit ~/.cpan/CPAN/myconfig.pm) (for some modules you might need to install manually instead of cpan, for me they are Readonly and Module::Build::Tiny) export PERL5LIB=pathTo/lib/perl5/ **You might get error: (use  ssh -X to login should solve it.)** Traceback (most recent call last): File "/dscrhome/yd44/yd44/python3.5/lib/python3.5/runpy.py", line 184, in _run_module_as_main "__main__", mod_spec) File "/dscrhome/yd44/yd44/python3.5/lib/python3.5/runpy.py", line 85, in _run_code exec(code, run_globals) File "treeomics/__main__.py", line 747, in <module> main() File "treeomics/__main__.py", line 528, in main displayed_mutations=patient.present_mutations, put_driver_vars=put_driver_vars) File "treeomics/plots/plots_utils.py", line 75, in bayesian_hinton fig = plt.figure(figsize=(x_length / 20.0, y_length / 20.0), dpi=150)   # , frameon=False File "/dscrhome/yd44/yd44/python3.5/lib/python3.5/site-packages/matplotlib/pyplot.py", line 434, in figure **kwargs) File "/dscrhome/yd44/yd44/python3.5/lib/python3.5/site-packages/matplotlib/backends/backend_tkagg.py", line 81, in new_figure_manager return new_figure_manager_given_figure(num, figure) File "/dscrhome/yd44/yd44/python3.5/lib/python3.5/site-packages/matplotlib/backends/backend_tkagg.py", line 89, in new_figure_manager_given_figure window = Tk.Tk() File "/dscrhome/yd44/yd44/python3.5/lib/python3.5/tkinter/__init__.py", line 1868, in __init__ self.tk = _tkinter.create(screenName, baseName, className, interactive, wantobjects, useTk, sync, use) _tkinter.TclError: no display name and no $DISPLAY environment variable     1/22/2018 update: Somehow ssh -X can't solve the problem now. Using echo "backend: Agg" > ~/.config/matplotlib/matplotlibrc   seem to work. (also added this before importing pyplot: 
    
    
    import matplotlib
    matplotlib.use('Agg')

)
