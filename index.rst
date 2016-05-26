..
  Content of technical report.

  See http://docs.lsst.codes/en/latest/development/docs/rst_styleguide.html
  for a guide to reStructuredText writing.

  Do not put the title, authors or other metadata in this document;
  those are automatically added.

  Use the following syntax for sections:

  Sections
  ========

  and

  Subsections
  -----------

  and

  Subsubsections
  ^^^^^^^^^^^^^^

  To add images, add the image file (png, svg or jpeg preferred) to the
  _static/ directory. The reST syntax for adding the image is

  .. figure:: /_static/filename.ext
     :name: fig-label
     :target: http://target.link/url

     Caption text.

   Run: ``make html`` and ``open _build/html/index.html`` to preview your work.
   See the README at https://github.com/lsst-sqre/lsst-report-bootstrap or
   this repo's README for more info.

   Feel free to delete this instructional comment.

:tocdepth: 1

In order to test Differential Chromatic Refraction (DCR) correction algorithms we first need a metric that quantifies the severity of residual dipoles in difference images, in order to evaluate the performance of the correction. 
I used the StarFast simulator (http://dmtn-012.lsst.io, https://github.com/lsst-dm/starfast_simulator) to generate multiple realizations of a small field at u, g, and r bands and across a range of airmasses from 1.0 to 2.0.
I then used ingestSimImages.py and processEimage.py from obs_lsstSim to generate standard calibrated exposures, and ran standard LSST image differencing using imageDifference.py with a calibrated exposure near zenith used as the template (using GetCalexpAsTemplateTask).

.. figure:: /_static/Dipoles_ds9_fourpanel_f012.png
   :name: fig-dipole_fourpanel
   :target: https://github.com/lsst-dm/dmtn-019/tree/master/_static/Dipoles_ds9_fourpanel_f012.png


   A small region from the simulated images at airmass 1.3 differenced from a template at airmass 1.00. Left to right, top to bottom: u-band, g-band, r-band, and the g-band template image for reference.

.. figure:: /_static/ref_ugr_image.png
   :name: fig-ugr_image
   :target: https://github.com/lsst-dm/dmtn-019/tree/master/_static/ref_ugr_image.png

   False color image of the template images, with u-band = blue, g-band = green, and r-band = red


.. figure:: /_static/Masked_diaSrc_f0.png
   :name: fig-u_diffim_masked
   :target: https://github.com/lsst-dm/dmtn-019/tree/master/_static/Masked_diaSrc_f0.png

   Full u-band difference image with positive and negative source detections masked in dark/light blue, saturated sources masked in green, and the edges masked in yellow.

.. figure:: /_static/Masked_diaSrc_f1.png
   :name: fig-g_diffim_masked
   :target: https://github.com/lsst-dm/dmtn-019/tree/master/_static/Masked_diaSrc_f1.png

   Full g-band difference image with positive and negative source detections masked in dark/light blue, saturated sources masked in green, and the edges masked in yellow.

.. figure:: /_static/Masked_diaSrc_f2.png
   :name: fig-r_diffim_masked
   :target: https://github.com/lsst-dm/dmtn-019/tree/master/_static/Masked_diaSrc_f2.png

   Full r-band difference image with positive and negative source detections masked in dark/light blue, saturated sources masked in green, and the edges masked in yellow.


.. figure:: /_static/Dipole_severity_metric_plot.png
   :name: fig-dipole_severity
   :target: https://github.com/lsst-dm/dmtn-019/tree/master/_static/Dipole_severity_metric_plot.png

  