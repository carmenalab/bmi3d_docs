# bmi3d_docs

How to update the web docs for http://carmenalab.github.io/bmi3d_docs/::
  
  # Make a directory to store the HTML files
  lab@arc:~$ mkdir ~/code/docbmi3d/
  lab@arc:~$ cd ~/code/docbmi3d/
  # clone this repository into that directory and rename it to 'html'
  lab@arc:~/code/docbmi3d$ git clone https://github.com/carmenalab/bmi3d_docs.git html
  lab@arc:~/code/docbmi3d$ ls
  html
  lab@arc:~/code/docbmi3d$ cd html/
  # switch branches onto the special gh-pages branch, which github knows to interpret as an HTML page
  lab@arc:~/code/docbmi3d/html$ git checkout gh-pages
  Branch gh-pages set up to track remote branch gh-pages from origin.
  Switched to a new branch 'gh-pages'
  # Change the sphinx-docs makefile to build HTML files into the git repo 'html'
  lab@arc:~/code/docbmi3d/html$ cd ~/code/bmi3d
  lab@arc:~/code/bmi3d$ cd docs
  lab@arc:~/code/bmi3d/docs$ vim Makefile 
  # Change BUILDDIR      = /home/lab/code/docbmi3d/ # (the parent of the 'html' folder)
  # Build the HTML files
  lab@arc:~/code/bmi3d/docs$ make html
  lab@arc:~/code/bmi3d/docs$ cd ~/code/docbmi3d/html/
  # commit and push to the bmi3d_docs repo with the newly created HTML files
  lab@arc:~/code/docbmi3d/html$ git commit -a -m "update"
  lab@arc:~/code/docbmi3d/html$ git push origin gh-pages
