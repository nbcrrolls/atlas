atlas
=====

Roll for Atlas Computational Solvent Mapping with Flexibility

Software info
-------------------

Version 1.7.0

Performs global search of the entire protein surface for regions that 
bind a number of small organic probe molecules.
Original software and server are at BU: http://ftmap.bu.edu/home.php

Current software (binary) distro is atlas-1.7.0-nopython.tar.bz2 recevied from D. Hall
(agreement with Amaro lab). Repack the distro after fixing the bugs and removign extra
files from examples/:

- src/atlas.py  
   * line 923: rm env={} (subprocess.call([prms.atlas_base+'/pdb2pqr/pdb2pqr.py'...)  
   * line 936: cast to str env_dictionary['OMP_NUM_THREADS'] = str(prms.np)  
- src/run_atlas.py  
   * line 85: cast to str env_dictionary['OMP_NUM_THREADS'] = str(prms.np)  
   
Roll info
-----------

Roll installs :

   * atlas software on all nodes in /opt/atlas-1.7.0/
   * SGE parallel enviornment "threaded" with allocation rule "pe_slots" on frontend.
   * python wrappers for ATLAS and FLEX opal web services and respective xml files on opal server 
