.. meerkathi-docs documentation master file, created by
   sphinx-quickstart on Mon Feb 18 15:04:26 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.
 
.. _get_data:
 
==========================================
get_data
==========================================
 
.. toctree::
   :maxdepth: 1
 
Download and/or convert/unarchive data so that its in the MS format for further processing



-------------------------------------
**order**
-------------------------------------

  *int*, *optional*

  Workers are executed in ascedning order based on this value.



-------------------------------------
**dataid**
-------------------------------------

  *optional*

  Basename of MS. For MeerKAT data to be downloaded by MeerKATHI, this should be the data ID of the observation



-------------------------------------
**mvftoms**
-------------------------------------

  Convert HDF5/MVF files in data_path to MS files; the latter are written to msdir; also creates a MS.TAR file. (This only works for MeerKAT HDF5 files)

    **enable**
      *bool*, *optional*

      Execute this segment

    **tar**
      *bool*, *optional*

      Create a tarbal of the converted MS.

    **channel_range**
      *str*, *optional*

      Only exctract channels in this range (0-based, inclusive; comma seperated string)

    **full_poll**
      *bool*, *optional*

      Extract all four correlations instead of only the XX,YY



-------------------------------------
**untar**
-------------------------------------

  Unarchive from MS from a archive file.

    **enable**
      *bool*, *optional*

      Execute this segment

    **tar_options**
      *str*, *optional*

      Options to parse to 'tar' command



-------------------------------------
**combine**
-------------------------------------

  Virtually concatenate MSs and proceed with the combined MS

    **enable**
      *bool*, *optional*

      Execute this section

    **reset**
      *bool*, *optional*

      Delete concatenated MS if it exists. Else, proceed with existing MS

    **tar**
      Create a tarbal of the converted MS

    **untar**
      Unarchive from MS from a archive file.
