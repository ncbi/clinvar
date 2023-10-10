# Changes to tab-delimited files

To support the changes for somatic classifications, we will update the tab-delimited files that include the classification.

*IMPORTANT*: The sample tab-delimited files are fake data, for testing purposes only! All the data in the sample ftp files are fake, including the submitters, the variants, the tumor types, and all supporting data. It is dummy data only to demonstrate what kind of data would be in each field and so that you have test data to use when updating your code. Do NOT incorporate this data into your production system.

## organization_summary.txt
 * New fields will be added for "somatic clinical impact values submitted", "somatic oncogenicity values submitted".
 * Sample file: [organization_summary.txt](organization_summary.txt).

## submission_summary.txt 
 * New fields will be added for "SomaticClinicalImpact", "Oncogenicity".
 * An SCV with a classification of SomaticClinicalImpact or Oncogenicity will use the existing columns for "ReviewStatus", "DateLastEvaluated", "SubmittedPhenotypeInfo", "ReportedPhenotypeInfo" to report the relevant data.
 * The field ClinicalSignificance will be retained to report the germline classification, and the existing columns for "ReviewStatus", "DateLastEvaluated", "SubmittedPhenotypeInfo", "ReportedPhenotypeInfo" to report the relevant data.
 * Sample file: [submission_summary.txt](submission_summary.txt).

## VCF
 * INFO tags related to Somatic Clinical Impact will be added (SCI, SCIDN, SCIDISDB, SCIREVSTAT).
 * INFO tags related to Oncogenicity will be added (ONC, ONCDN, ONCDISDB, ONCREVSTAT, ONCCONF).
 * INFO tags related to SomaticClinicalImpact for included variants will be added (SCIINCL, SCIDNINCL, SCIDISDBINCL).
 * INFO tags related to Oncogenicity for included variants will be added (ONCINCL, ONCDNINCL, ONCDISDBINCL).
 * The existing INFO tags CLNSIG, CLNDN, CLNDNINCL, CLNDISDB, CLNDISDBINCL, CLNREVSTAT, CLNSIGCONF, CLNSIGINCL will be retained to report data for germline classifications.
 * Definitions for the new tags are included in the sample file; they follow a pattern established by the existing INFO tags for germline data.
 * Sample file: [clinvar.vcf](clinvar.vcf).


## variant_summary.txt
 * New fields for "SomaticClinicalImpact", "SomaticClinicalImpactLastEvaluated", "ReviewStatusClinicalImpact", "Oncogenicity", "OncogenicityLastEvaluated", "ReviewStatusOncogenicity" will be added.
 * The existing fields ClinicalSignificance, ClinSigSimple, LastEvaluated, ReviewStatus will be retained to report data for germline classifications.
 * Sample file: [variant_summary.txt](variant_summary.txt).
