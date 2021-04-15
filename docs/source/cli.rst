Command Line Interface
======================

.. code-block:: console

    $ amimspy --help

    Executing amimspy version 0.1.0
    usage: __main__.py [-h]
                       {process-scans,process-samples,hdf5-pm-to-txt,hdf5-pls-to-txt}
                       ...

    Python package for processing acoustic mist ionisation-mass spectrometry
    -based metabolomics and lipidomics data

    positional arguments:
      {process-scans,process-samples,hdf5-pm-to-txt,hdf5-pls-to-txt}
        process-scans       Process and align scans within samples.
        process-samples     Process and align samples.
        hdf5-pm-to-txt      Write HDF5 output (peak matrix) to text format.
        hdf5-pls-to-txt     Write HDF5 output (peak lists) to text format.

    optional arguments:
      -h, --help            show this help message and exit


.. code-block:: console

    $ amimspy process-scans --help

    Executing amimspy version 0.1.0
    usage: __main__.py process-scans [-h] -i source [source ...] -ms source
                                 [source ...] -o OUTPUT -f FAILED_WELLS -pr
                                 PROCESSED_SCANS
                                 [-m {all_scans,on_scans,off_scans,on_scan_no_edge}]
                                 [-d ID_SNR] [-t ID_TOL] [-s SNR_THRESHOLD]
                                 [-n MIN_SCANS] [-r RSD_THRESHOLD]
                                 [-fr MIN_FRACTION] -p PPM [-l METALIST]

    optional arguments:
      -h, --help            show this help message and exit
      -i source [source ...], --input source [source ...]
                            Absolute or relative path to the *.mzml file(s). Must
                            be in same order as 'metascans *txt files'
      -ms source [source ...], --metascans source [source ...]
                            Absolute or relative path to the comma-delimited *.txt
                            metadata file. Must be in same order and 'input' *mzml
                            files. Header names must contain and be in the
                            following order names =['barcode', 'date/time', 'row',
                            'col', 'scan', 'ejection time', 'NA'] as output by MS-
                            Parser tool
      -o OUTPUT, --output OUTPUT
                            Absolute or relative path to the output file
      -f FAILED_WELLS, --failed-wells FAILED_WELLS
                            Absolute or relative path to the *.txt output of which
                            well failed
      -pr PROCESSED_SCANS, --processed_scans PROCESSED_SCANS
                            Absolute or relative path to the *.txt output of which
                            well failed
      -m {all_scans,on_scans,off_scans,on_scan_no_edge}, --method {all_scans,on_scans,off_scans,on_scan_no_edge}
                            Method to define which scans to extract data from.
                            DEFAULT = on_scans_no_edge
      -d ID_SNR, --id-snr ID_SNR
                            For identifying on/off scans: Hard SNR threshold for
                            differentiating between on/off scans. DEFAULT = 15
      -t ID_TOL, --id-tol ID_TOL
                            For identifying on/off scans: Number of features with
                            SNR > threshold to tolerate in off scans. DEFAULT = 3
      -s SNR_THRESHOLD, --snr-threshold SNR_THRESHOLD
                            SNR threshold to remove noise features. DEFAULT = 2
      -n MIN_SCANS, --min-scans MIN_SCANS
                            Minimum number of scans required to be labelled on
                            within a well for sample to be taken forward. DEFAULT
                            = 0
      -r RSD_THRESHOLD, --rsd-threshold RSD_THRESHOLD
                            RSD filter (scan level): Threshold of RSD of features
                            across scans in sample for it to be retained. DEFAULT
                            = None
      -fr MIN_FRACTION, --min-fraction MIN_FRACTION
                            Minimum fraction a peak has to be present. Use 0.0 to
                            not apply this filter.
      -p PPM, --ppm PPM     Aligning scans: m/z precision (ppm) to align scans in
                            sample - REQUIRED PARAMETER!
      -l METALIST, --metalist METALIST
                            Absolute or relative path to the tab-delimited *.txt
                            file that include the name of the data files (*.mzml)
                            and meta data. Column names: filename, replicate,
                            batch, injectionOrder, classLabel.
