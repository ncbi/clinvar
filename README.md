# ClinVar
[ClinVar](https://www.ncbi.nlm.nih.gov/clinvar/) [GitHub](https://github.com/ncbi/clinvar)

We released changes to the ClinVar XML files and our submission spreadsheet templates on January 29 2024; these changes will improve support for classifications of somatic variants in ClinVar

To help file submitters prepare for this change, we are making the updated spreadsheet templates available for review with a [note explaining changes](submission_templates/README.md).
([SubmissionTemplate.xlsx](submission_templates/SubmissionTemplate.xlsx), [SubmissionTemplateLite.xlsx](submission_templates/SubmissionTemplateLite.xlsx) and [SubmissionTemplateSomatic.xlsx](submission_templates/SubmissionTemplateSomatic.xlsx))

The production endpoint for the Submission API supports submission of somatic variants as of May 15 2024; the test endpoint was made available on April 11 2024. Details can be found [in the README for the API schema](submission_api_schema/README.md).

Submission of somatic variants through the submission wizard and SCV update forms will be added later in 2024.

To help our XML users prepare for this change, we are providing documentation before we release this feature. The documentation includes:
- a preview of the updated XSDs for both [RCV](xsds_preview/clinvar_public.xsd) and [VCV](xsds_preview/variation_archive.xsd) XMLs
- a list of [changes](xsds_preview/xsd_change_highlights.xlsx) to both XSDs 
- [sample XMLs](sample_xmls/) for both RCV and VCV
- [sample variation web page and search snapshots](sample_web_snapshots/)
- [sample_tab_delimited](sample_tab_delimited/) for tab-delimited FTP files
- [submission api schema](submission_api_schema/) for API schema
- a [note](ClassificationOnClinVar.md) explaining Classification on ClinVar aggregated records
- a [note](ReviewStatus.md) explaining Review Status on ClinVar records.
- a [note](FTPSiteXmlChanges.md) showing the preview of FTP folder structure and filenames for XML files.
- a [note](FTPSiteXsdChanges.md) showing the preview of FTP folder structure and filenames for XSD files.
- a [note](E-utilities.md) providing details of efetch to access XML records in both new and old XML format.

*IMPORTANT*: The sample XML is fake data, for testing purposes only! All of the data in the sample XML is fake, including the submitters, the variants, the tumor types, and all supporting data. It is dummy data only to demonstrate what kind of data would be in each field and so that you have test data to use when updating your code. Do NOT incorporate this data into your production system.

Once the new XML format is available, we will support the old XML format through June 2024. We encourage our XML users to start the transition to the new XML format as soon as you can, and to contact us at clinvar@ncbi.nlm.nih.gov with any questions.
