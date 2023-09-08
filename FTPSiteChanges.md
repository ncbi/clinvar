# Changes to the FTP site

To support both the old format of our XML and the new format that includes changes for somatic classifications, we will update the FTP directory structure for our XML files.

## File names

Files with the old format will retain the same names:
    - ClinVarVariationRelease_YYYY-MM.xml.gz for VCV XML 
    - ClinVarFullRelease_YYYY-MM.xml.gz for RCV XML
However, the path for these files will change – see the proposed directory structure below. To continue using the old format, you only need to change the path to the file.

Files with the new format will be named as follows:
    - ClinVarVCVRelease_YYYY-MM.xml.gz for VCV XML
    - ClinVarRCVRelease_YYYY-MM.xml.gz for RCV XML

## Directory structure

The major changes to the directory structure are:
* We will make the new VCV XML available in the main directory /pub/clinvar/xml. 
    - This XML contains ClinVar data aggregated by variant, consistent with the default web display, and it is more widely used than RCV XML. 
    - If you are using the RCV XML, we encourage you to switch to the VCV XML. If you still prefer the RCV XML, we’d love to hear from you – please contact us at clinvar@ncbi.nlm.nih.gov with your opinion.
* The main directory /pub/clinvar/xml will have subdirectories for weekly releases and archives of the VCV XML.
* The RCV XML will be in a subdirectory RCV_release. This subdirectory will have subdirectories for weekly releases and archives of the RCV XML.
* The main directory /pub/clinvar/xml will have subdirectories for VCV and RCV XML in the old format. You can point your existing code to these subdirectories to continue using XML in the old format until we discontinue it.



Proposed FTP folder Structure for
https://ftp.ncbi.nlm.nih.gov/pub/clinvar/xml/

<pre>
|   ClinVarVCVRelease_00-lastest.xml.gz
|   ClinVarVCVRelease_00-lastest.xml.gz.md5
|   ClinVarVCVRelease_2023-11.xml.gz
|   ClinVarVCVRelease_2023-11.xml.gz.md5
|   ...
|   ...
|   _README.txt
+---sample_xml   
+---archive
|   |   ClinVarVCVRelease_2023-11.xml.gz
|   |   ClinVarVariationRelease_2023-11.xml.gz
|   |   ...
+---weekly_release
|   |   ClinVarVCVRelease_00-lastest_weekly.xml.gz
|   |   ClinVarVCVRelease_00-lastest_weekly.xml.md5
|   |   ...
+---RCV_release
|   |   ClinVarRCVRelease_00-lastest.xml.gz
|   |   ClinVarRCVRelease_00-lastest.xml.gz.md5
|   |   ClinVarRCVRelease_2023-11.xml.gz
|   |   ClinVarRCVRelease_2023-11.xml.md5
|   |   ...
|   +---archive
|   |   |   ClinVarRCVRelease_2023-11.xml.gz  
|   |   |   ClinVarFullRelease_2023-11.xml.gz 
|   |   |   ...
|   \---weekly_release
|       |   ClinVarRCVRelease_00-lastest_weekly.xml.gz
|       |   ClinVarRCVRelease_00-lastest_weekly.xml.md5
+---RCV_xml_old_format
|   |   ClinVarFullRelease_00-latest.xml.gz
|   |   ClinVarFullRelease_00-latest.xml.gz.md5
|   |   ClinVarFullRelease_2023-01.xml.gz
|   |   ClinVarFullRelease_2023-01.xml.md5
|   |   ClinVarFullRelease_2023-02.xml.gz
|   |   ClinVarFullRelease_2023-02.xml.md5
|   |   ...
|   \---weekly_release
|       |   ClinVarFullRelease_00-latest_weekly.xml.gz
|       |   ClinVarFullRelease_00-latest_weekly.xml.gz.md5
|       |   ...
\---VCV_xml_old_format
    |   ClinVarVariationRelease_00-latest.xml.gz
    |   ClinVarVariationRelease_00-latest.xml.gz.md5
    |   ClinVarVariationRelease_2023-01.xml.gz
    |   ClinVarVariationRelease_2023-01.xml.gz.md5
    |   ...
    \---weekly_release
        |   ClinVarVariationRelease_00-latest_weekly.xml.gz
        |   ClinVarVariationRelease_00-latest_weekly.xml.gz.md5
        |   ...
</pre>        
