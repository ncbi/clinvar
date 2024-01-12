# Changes to the FTP site for XSD files

To support both the old format of XSD and the new format that includes changes for somatic classifications, we will update the FTP directory structure for our XSD files.

## XSD File names

Files with the old format will retain the same names:
   - variation_archive_1.17.xsd for VCV XSD
   - clinvar_public_1.72.xsd for RCV XSD

However, the path for these files will change – see the proposed directory structure below. To continue using the old format, you only need to change the path to the file.

Files with the new format will be named as follows:
   - ClinVar_VCV_2.0.xsd for VCV XSD
   - ClinVar_RCV_2.0.xsd for RCV XSD

the major version of XSD in new format will increase to 2, while XSD of old format has major version of 1.


## XSD Directory structure

The major changes to the directory structure are:
* We will make the XSD of VCV in new format available in the main directory /pub/clinvar/xsd_public.
* The XSD of RCV in new format will be in a subdirectory RCV.
* The main directory /pub/clinvar/xsd_public will have subdirectories for VCV and RCV XSD in the old format. You can point your existing code to these subdirectories to continue using XSD in the old format until we discontinue it.
* The XSD difference comparison file between different version will be in /pub/clinvar/release_notes, like ClinVar_RCV_2.1_diff.html for RCV, and ClinVar_VCV_2.1_diff.html for VCV

Proposed FTP folder Structure for XSD files
https://ftp.ncbi.nlm.nih.gov/pub/clinvar/xsd_public

<pre>
|   ClinVar_VCV_2.0.xsd
|   ClinVar_VCV_2.0.xsd.md5
|   ClinVar_VCV_weekly.xsd
|   ClinVar_VCV_weekly.xsd.md5
|   ClinVar_VCV.xsd
|   ClinVar_VCV.xsd.md5
|   ...
|   ...
+---RCV
|   |   ClinVar_RCV_2.0.xsd
|   |   ClinVar_RCV_2.0.xsd.md5
|   |   ClinVar_RCV_weekly.xsd
|   |   ClinVar_RCV_weekly.xsd.md5
|   |   ClinVar_RCV.xsd
|   |   ClinVar_RCV.xsd.md5
|   |   ...
+---RCV_xsd_old_format
|   |   clinvar_public_1.72.xsd
|   |   clinvar_public_1.72.xsd.md5
|   |   clinvar_public_weekly.xsd
|   |   clinvar_public_weekly.xsd.md5
|   |   clinvar_public.xsd
|   |   clinvar_public.xsd.md5
|   |   ...
+---VCV_xsd_old_format
|   |   variation_archive_1.17.xsd
|   |   variation_archive_1.17.xsd.md5
|   |   variation_archive_weekly.xsd
|   |   variation_archive_weekly.xsd.md5
|   |   variation_archive.xsd
|   |   variation_archive.xsd.md5
|   |   ...
</pre>        
