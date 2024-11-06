# Changes to the ClinVar submission spreadsheet templates

As part of the changes to ClinVar to support classifications of somatic variants, we are updating the submission spreadsheet templates. Older versions will not be supported. We will announce a release date for the new submission templates when we get closer to the release.

## Updates to the existing templates
The existing templates, [SubmissionTemplate.xlsx](SubmissionTemplate.xlsx) and [SubmissionTemplateLite.xlsx](SubmissionTemplateLite.xlsx), will continue to be used to submit classifications of germline variants. Both templates will be updated to use the term “classification” instead of “clinical significance”. This change is to clarify that data in ClinVar should represent variant-level classifications for a disease, rather than an interpretation of the clinical significance of a variant for a specific patient.

The following columns in SubmissionTemplate.xlsx and SubmissionTemplateLite.xlsx will be renamed:
-	“Clinical significance” renamed “Germline classification”
-	“Clinical significance citations” renamed “Classification citations”
-	“Citations or URLs for clinical significance without database identifiers” renamed “Citations or URLs for classification without database identifiers”
-	“Comment on clinical significance” renamed “Comment on classification”
-	“Explanation if clinical significance is other or drug response” renamed “Explanation if classification is other or drug response”
-	“Testing laboratory interpretation” renamed “Testing laboratory classification”

## New template for somatic variants
A new template, [SubmissionTemplateSomatic.xlsx](SubmissionTemplateSomatic.xlsx), will be added for submission of somatic variants classified for cancer. It is based on SubmissionTemplate.xlsx with some changes.

The following columns are not found in SubmissionTemplateSomatic.xlsx:
-	Clinical significance
-	Assertion score
-	Mode of inheritance
-	Explanation if clinical significance is other or drug response
-	Drug response condition
-	Number of families tested
-	Number of families with variant
-	Number of families with segregation observed
-	Secondary finding

The following columns are added to SubmissionTemplateSomatic.xlsx:
-	Somatic classification of clinical impact (Tiers I-IV based on the AMP/ASCO/CAP recommendation in PMID:27993330)
-	Assertion type for clinical impact
    -	therapeutic: therapeutic: sensitivity/response; resistance; reduced sensitivity
    -	diagnostic: supports diagnosis; excludes diagnosis
    -	prognostic: better outcome, poor outcome
-	Drug relevant for therapeutic assertion of clinical impact
-	Oncogenicity classification
-	Presence of somatic variant in normal tissue
-	Somatic variant allele fraction
