# ClinVar Submission API

ClinVar's current Submission API schema is [submission_api_schema.json](submission_api_schema.json) and more details can be found [here](https://www.ncbi.nlm.nih.gov/clinvar/docs/api_http/).

We plan to introduce some changes to the ClinVar Submission API schema to improve support for submission of somatic variants through the API.
<br />[Preview of proposed API submission Schema to support Somatic Variant Classifications](submission_api_schema_proposed.json).


Similar to the somatic spreadsheet submission template, the proposed schema offers two types of classification for somatic variants: "oncogenicityClassification" and "clinicalImpactClassification".  More information about the types of classifications in ClinVar is available on our website: https://www.ncbi.nlm.nih.gov/clinvar/docs/clinsig/. Consequently, three new submission set objects are introduced: "oncogenicitySubmission" and "clinicalImpactSubmission" for somatic variants and "germlineSubmission" for germline variants. 
<br />Note: We plan to deprecate the "clinvarSubmission" submission set object in the future. Though this proposed schema remains backward compatible with the "clinvarSubmission", we strongly recommend transitioning to the equivalent "germlineSubmission".


Highlights of differences between submission set objects:
|Submission components|germlineSubmission|clinicalImpactSubmission|oncogenicitySubmission|
| ---------------------------------------------------------- | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
|Observation| |presenceOfSomaticVariantInNormalTissue <br> somaticVariantAlleleFraction|presenceOfSomaticVariantInNormalTissue <br> somaticVariantAlleleFraction|
|Conditions|drug response| | |
|Classification|germlineClassification <br> modeOfInheritance <br> customAssertionScore <br> explanationOfDrugResponse <br> explanationOfOtherGermlineClassification <br /> <br /> *All these properties use the term "germlineClassification" instead of "clinical significance" (The term used in 'clinvarSubmission' object) |clinicalImpactClassification|oncogenicityClassification|

Differences between current and proposed schema: [api_submission_schema_diff.html](api_schema_diff.html)

## Examples:
*IMPORTANT*: The json files are fake data, for testing purposes only! Do NOT incorporate this data into your production system.

[Germline submission](sample_api_submissions/sample_germline_hgvs_submission.json)

[Oncogenicity submission](sample_api_submissions/sample_oncogenicity_hgvs.json)

[Clinical Impact submission](sample_api_submissions/sample_clinical_impact_hgvs.json)

[Deprecated Clinical Significance submission](sample_api_submissions/sample_clinical_significance_hgvs_submission.json)
