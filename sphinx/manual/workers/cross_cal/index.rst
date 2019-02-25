.. meerkathi-docs documentation master file, created by
   sphinx-quickstart on Mon Feb 18 15:04:26 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.
 
.. _cross_cal:
 
==========================================
cross_cal
==========================================
 
.. toctree::
   :maxdepth: 1
 
Carry out Cross calibration of the data (delay, bandpass and gain calibration)



-------------------------------------
**enable**
-------------------------------------

  *bool*, *optional*

  Execute this segment.



-------------------------------------
**order**
-------------------------------------

  *int*, *optional*

  Workers are executed in ascending order based on this value.



-------------------------------------
**otfdelay**
-------------------------------------

  *bool*, *optional*

  Set whether to apply the delay calibration on the fly when solving for other calibration terms.



-------------------------------------
**uvrange**
-------------------------------------

  *str*, *optional*

  Set the U-V range for data selection, e.g. '>50'.



-------------------------------------
**label**
-------------------------------------

  *str*, *optional*

  Label for output files.



-------------------------------------
**clear_cal**
-------------------------------------

  Initializes dataset for calibration using CASA

    **enable**
      *bool*, *optional*

      Execute intialization step

    **field**
      *optional*

      fields to initialize

    **addmodel**
      *bool*, *optional*

      Intializes scratch MODEL_DATA column



-------------------------------------
**set_model**
-------------------------------------

  Essentially setjy task from CASA.

    **enable**
      *bool*, *optional*

      Execute the setjy task.

    **meerkathi_model**
      *bool*, *optional*

      Force disable built-in models in MeerKATHI (NOT RECOMMENDED!)

    **no_verify**
      *bool*, *optional*

      Enables setting standard manually.

    **field**
      *optional*

      Set the field to carry out setjy on. Specify either the field number, name or even as 'fcal' corresponding to field specification in observation config.

    **threads**
      *int*, *optional*

      Set the number of threads to use when predicting local sky model using MeqTrees.



-------------------------------------
**delay_cal**
-------------------------------------

  Carry out delay correction calibration (using gaincal task from CASA).

    **enable**
      *bool*, *optional*

      Execute delay correction calibration.

    **combine**
      *str*, *optional*

      Parameter to combine different data axis for solving.

    **solint**
      *str*, *optional*

      Solution interval for delay-correction calibration.

    **minnrbl**
      *int*, *optional*

      Minimum number of baselines required (per antenna) for solving.

    **minsnr**
      *int*, *optional*

      Minimum required SNR for solutions.

    **field**
      *optional*

      Set the field to estimate the delay correction from. Specify either the field number, name or even as 'fcal' corresponding to field specification in observation config.

    **plot**
      Plotting dignostics plots for delay correction calibration.

    **flag**
      Flagging based on delay correction solutions.



-------------------------------------
**bp_cal**
-------------------------------------

  Carry out bandpass calibration (using bandpass task from CASA)

    **enable**
      *bool*, *optional*

      Executes bandpass calibration.

    **combine**
      *str*, *optional*

      Parameter to combine different data axis for solving.

    **field**
      *optional*

      Set the field to estimate the bandpass from. Specify either the field number, name or even as 'bpcal' corresponding to field specification in observation config.

    **minnrbl**
      *int*, *optional*

      Minimum number of baselines required (per antenna) for solving.

    **minsnr**
      *int*, *optional*

      Minimum required SNR for solutions.

    **solnorm**
      *bool*, *optional*

      Normalize average solution amplitudes to unity.

    **solint**
      *str*, *optional*

      Solution interval for delay-correction calibration.

    **set_refant**
      *bool*

      Should a reference antenna be used for this calibration

    **remove_ph_time_var**
      *bool*, *optional*

      Remove large temporal phase variations from bandpass calibrator before solving.

    **plot**
      Plotting dignostics plots for bandpass correction calibration.



-------------------------------------
**gain_cal_flux**
-------------------------------------

  Carry out gain calibration on the flux calibrator field.

    **enable**
      *bool*, *optional*

      Execute gain calibration on the flux calibrator field.

    **combine**
      *str*, *optional*

      Parameter to combine different data axis for solving.

    **field**
      *optional*

      Set the field to estimate the gain from. Specify either the field number, name or even as 'fcal' corresponding to field specification in observation config.

    **minnrbl**
      *int*, *optional*

      Minimum number of baselines required (per antenna) for solving.

    **minsnr**
      *int*, *optional*

      Minimum required SNR for solutions.

    **solint**
      *str*, *optional*

      Time solution interval

    **set_refant**
      *bool*, *optional*

      Should a reference antenna be used for this calibration

    **plot**
      Plotting dignostics plots for flux calibrator corrections.



-------------------------------------
**gain_cal_gain**
-------------------------------------

  Carry out gain calibration on the gain calibrator field.

    **enable**
      *bool*, *optional*

      Execute gain calibration on the gain calibrator field.

    **combine**
      *str*, *optional*

      Parameter to combine different data axis for solving.

    **field**
      *optional*

      Set the field to estimate the gain from. Specify either the field number, name or even as 'gcal' corresponding to field specification in observation config.

    **minnrbl**
      *int*, *optional*

      Minimum number of baselines required (per antenna) for solving.

    **minsnr**
      *int*, *optional*

      Minimum required SNR for solutions.

    **solint**
      *str*, *optional*

      Time solution interval

    **set_refant**
      *bool*

      Should a reference antenna be used for this calibration

    **plot**
      Plotting dignostics plots for gain calibrator corrections.



-------------------------------------
**transfer_fluxscale**
-------------------------------------

  Transfers fluxscale from the flux calibrator field to the gain calibrator.

    **enable**
      *bool*, *optional*

      Executes transferring flux scale.

    **reference**
      *optional*

      Field to transfer flux sale from. Specify either the field number, name or even as 'gcal' corresponding to field specification in observation config.

    **transfer**
      *optional*

      Field to transfer flux scale to. Specify either the field number, name or even as 'gcal' corresponding to field specification in observation config.

    **plot**
      Enables plotting gain amplitudes for Flux and Gain calibrator field.



-------------------------------------
**apply_delay_cal**
-------------------------------------

  Apply the delay correction calibration table to specified fields via the CASA applycal task.

    **enable**
      *bool*, *optional*

      Executes application of delay correction calibration table.

    **field**
      *optional*

      Field to select in the delay correction calibration table. Specify either the field number, name or as corrsponding to field spec in observation config, e.g. 'bpcal'.

    **applyto**
      *optional*

      Field(s) to apply the delay correction calibration table to. Specify either the field number, name or as corrsponding to field spec in observation config, e.g. 'bpcal, gcal, target'.

    **applymode**
      *str*, *optional*

      Calibration mode, the default being "calflag" - calibrates and applies flags from solutions. See CASA documentation for info on other modes.



-------------------------------------
**apply_bp_cal**
-------------------------------------

  Apply the bandpass table to specified fields via the CASA applycal task.

    **enable**
      *bool*, *optional*

      Executes application of bandpass table.

    **field**
      Field to select in the bandpass table. Specify either the field number, name or as corrsponding to field spec in observation config, e.g. 'bpcal'.

    **applyto**
      *optional*

      Field(s) to apply the bandpass table to. Specify either the field number, name or as corrsponding to field spec in observation config, e.g. 'bpcal, gcal, target'.

    **applymode**
      *str*, *optional*

      Calibration mode, the default being "calflag" - calibrates and applies flags from solutions. See CASA documentation for info on other modes.



-------------------------------------
**apply_gain_cal_gain**
-------------------------------------

  Apply the gain calibration table to specified fields via the CASA applycal task.

    **enable**
      *bool*, *optional*

      Executes application of gain calibration table.

    **field**
      Field to select in the gain calibration table. Specify either the field number, name or as corrsponding to field spec in observation config, e.g. 'gcal'.

    **applyto**
      *optional*

      Field(s) to apply the gain calibration table to. Specify either the field number, name or as corrsponding to field spec in observation config, e.g. 'bpcal, gcal, target'.

    **applymode**
      *str*, *optional*

      Calibration mode, the default being "calflag" - calibrates and applies flags from solutions. See CASA documentation for info on other modes.



-------------------------------------
**apply_transfer_fluxscale**
-------------------------------------

  Apply the fluxscale table to specified fields via the CASA applycal task.

    **enable**
      *bool*, *optional*

      Executes application of fluxscale table.

    **field**
      Field to select in the fluxscale table. Specify either the field number, name or as corrsponding to field spec in observation config, e.g. 'gcal'.

    **applyto**
      *optional*

      Field(s) to apply the fluxscale table to. Specify either the field number, name or as corrsponding to field spec in observation config, e.g. 'bpcal, gcal, target'.

    **applymode**
      *str*, *optional*

      Calibration mode, the default being "calflag" - calibrates and applies flags from solutions. See CASA documentation for info on other modes.



-------------------------------------
**autoflag_closure_error**
-------------------------------------

  Flag closure errors and systematic issues based on calibrated calibrator phase.

    **enable**
      *bool*, *optional*

      Execute flagging closure errors etc.

    **scan_to_scan_threshold**
      *int*, *optional*

      Sigma spread above the rest of the scans per field per channel.

    **baseline_to_group_threshold**
      *int*, *optional*

      Sigma above array median phase spread per scan per field per channel.

    **column**
      *str*, *optional*

      MS column to use.

    **fields**
      *str*, *optional*

      Fields to flag. Either set 'auto' or specify as 'gcal, bpcal, target'

    **calibrator_fields**
      *str*, *optional*

      Calibrator fields to estimate the closure errors etc. from.

    **threads**
      *int*, *optional*

      Number of cores to use to carry out this process.



-------------------------------------
**flagging_summary**
-------------------------------------

  Prints out the buther's bill, i.e. data flagging summary at the end of cross calibration process.

    **enable**
      *bool*, *optional*

      Execute printing flagging summary.
