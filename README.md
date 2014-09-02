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
   * line 922: rm env={} (subprocess.call([prms.atlas_base+'/pdb2pqr/pdb2pqr.py'...)  
   * line 934: cast to str env_dictionary['OMP_NUM_THREADS'] = str(prms.np)  
   * line 1367: change '.???.sdf' to '.*.sdf' (per D. Hall email Aud 20.)
   * line 1170: bug fix for  flex_residue_min()

- src/run_atlas.py  
   * line 85: cast to str env_dictionary['OMP_NUM_THREADS'] = str(prms.np)  
   * line 169: add bug fix per D. Hall email Sep 2. 
   
Roll info
-----------

Roll installs :

   * atlas software on all nodes in /opt/atlas-1.7.0/
   * SGE parallel enviornment "threaded" with allocation rule "pe_slots" on frontend.
   * python wrappers for ATLAS and FLEX opal web services and respective xml files on opal server 
