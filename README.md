# pycomlink

A python toolbox for MW link data processing and rain rate estimation

## Status
The basic functionality is already working. However, `pycomlink` is currently in ongoing development. Hence, there may be changes to the interface in the future.

## Features
 * Easily parse your MW link data and use and object oriented approach to do all the processing
 * Two wet/dry classification methods available
 * Different baseline methods availabel
 * One wet antenna estimation method available
 * 2D plots using IDW (preliminary version) 

## TODO
 * Fix problem with spectrogram from matplotlib.mlab in version > 1.3.0 
   (e.g. wet/dry stft method does not work with matplotlib version 1.4.0)
 * ~~~Function for saving Comlink object to HDF5~~~
     * Also write processing info to HDF5 file
     * Rethink HDF5 file structure, maybe something like the idea of ODIM-H5 would make sense
 * ~~~Query metadata (location, frequency, etc.) from database and parse to Comlink object~~~
 * Define crucial metadata entries and their naming convention
 * Resolve protection links
 * Move over processing methods from lirage
     * ~~~wet/dry std_dev~~~
         * ~~~Asure that std_dev method wet/dry index is centered over window~~~
     * ~~~wet/dty SFTF~~~
     * ~~~wet antenna Schleiss et al~~~
     * ~~~A-R transformation~~~
     * Update docstrings!!!
 * Maybe refactor Comlink class
     * seperate near-far (_nf) and far-near (_fn) (plus other signals, protection, etc.)
       and apply processing individually. Then just define one link as the ensemble of
       its signals (_nf, _fn, _nf_protect, ...)
 * Maybe use decorators to clean up tx_rx_pair loop stuff
 * Is 'mhz_a' in metadata the frequency from near- to far-end or far to near?