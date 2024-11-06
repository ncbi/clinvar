# ClinVar Submission API

ClinVar's Submission API schema is [submission_api_schema.json](submission_api_schema.json). 


Our production endpoint,  https://submit.ncbi.nlm.nih.gov/api/v1/submissions, supports [current submisison schema](submission_api_schema.json) <br />and the test endpoint, https://submit.ncbi.nlm.nih.gov/apitest/v1/submissions, supports [test schema](submission_apitest_schema.json). 
<br />[Details about endpoints and testing](https://www.ncbi.nlm.nih.gov/clinvar/docs/api_http/).
<br />If you have any comments or questions, please contact us at clinvar@ncbi.nlm.nih.gov.

<br />*Note: We plan to deprecate the "clinvarSubmission" submission set object from schema in the future. Though the current schema remains backward compatible with the "clinvarSubmission", we strongly recommend transitioning to the equivalent "germlineSubmission".*

## Examples:
*IMPORTANT*: The json files are fake data, for testing purposes only! Do NOT incorporate this data into your production system.

[Germline submission](sample_api_submissions/sample_germline_hgvs_submission.json)

[Oncogenicity submission](sample_api_submissions/sample_oncogenicity_hgvs.json)

[Clinical Impact submission](sample_api_submissions/sample_clinical_impact_hgvs.json)

[Deprecated Clinical Significance submission](sample_api_submissions/sample_clinical_significance_hgvs_submission.json)
