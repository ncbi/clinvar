# Classification on ClinVar aggregate records (VCV and RCV)


**Note**: We are moving away from the terms "clinical significance" and "interpretation" in favor of the term "classification". This change is to clarify
that data in ClinVar should represent variant-level classifications for a disease, rather than an interpretation of the clinical significance of a variant
for a specific patient.


ClinVar currently has a single field for "clinical significance". With the release of somatic classifications, we will have three types of classifications:
- "clinical significance" will be renamed "Germline classification"
- we will add a classification for "Somatic clinical impact", based on the AMP/ASCO/CAP Tiers (PMID 27993330)
- we will add a classification for "Oncogenicity", based on the ClinGen/CGC/VICC recommendation (PMID 36063163)


For each type of classification, ClinVar calculates an aggregate classification for the variant (VCV record) and for the variant/condition combination 
(RCV record). The aggregate classification is based on the classifications of that type that were provided in submitted records (SCV) for the VCV or RCV
record. Some classifications are given more weight in the aggregation, based on the review status of each SCV represented in the VCV or RCV. 
SCVs are used in this order of precedence:

  1. practice guideline: The classification from the practice guideline record is used as the classification on the VCV and RCV records, 
     no matter what other submitters may have reported.
     

  2. reviewed by expert panel: The classification from the expert panel record is used as the classification on the VCV and RCV records, if there is no record with higher precedence. Classifications from SCVs with lower review statuses are not considered.


  3. criteria provided, single submitter: The classifications from all submitted records with this review status are used to calculate the aggregate classification on the VCV and RCV records, if there is no SCV with higher precedence.


     For example, the classification on a single SCV record with review status "criteria provided, single submitter" supercedes classifications on multiple SCV records with lower review statuses.


  4. no assertion criteria provided: The classifications from all submitted records with this review status are used to calculate the aggregate 
    classification on the VCV and RCV records, if there is no SCV with higher precedence.


SCVs with review statuses of "no assertion provided" and "no assertion for the individual variant" do not contribute to the aggregate classification because these SCVs are submitted with no classification.


## Germline classification

Our public documentation for clinical significance will still apply to germline classification: 
https://www.ncbi.nlm.nih.gov/clinvar/docs/clinsig/#clinsig_agg


## Somatic clinical impact

For submission of somatic clinical impact, ClinVar will use the Tiers as described in AMP/ASCO/CAP Tiers (PMID 27993330). To clarify the tiers, we will 
append the term that indicates the level of significance, i.e.
  1. Tier I - Strong
  2. Tier II - Potential
  3. Tier III - Unknown
  4. Tier IV - Benign/Likely benign


The aggregate somatic clinical impact will be calculated as the highest tier that has been submitted for the variant, using review status of SCVs as described above.


Conflicts will not be calculated for somatic clinical impact. It is anticipated that it will be common to have multiple classifications for different tumor types and that these should not be considered conflicts. Therefore only the highest tier is reported for the aggregate classification. In addition, on the variant (VCV) web pages, we will show additional information in the aggregate section, including the tumor type or number of tumor types reported for the variant and if there are also SCVs with lower tiers of evidence submitted.


## Oncogenicity

For submission of oncogenicity, ClinVar will use the terms as described in the ClinGen/CGC/VICC recommendation (PMID 36063163), i.e.
  1. Oncogenic
  2. Likely oncogenic
  3. Uncertain significance
  4. Likely benign
  5. Benign


The aggregate oncogenicity classification will be calculated based on consensus or conflict in submitted records (SCVs) reporting oncogenicity, using review status of SCVs as described above.

If all SCVs in the calculation report the same classification, that term will used as the aggregate classification, e.g. if all SCVs report Oncogenic, the aggregate oncogenicity classification will be Oncogenic.

If SCVs in the calculation report different classifications, consensus and conflict will be calculated as follows:


|   Combination of terms from different submitters	|  Reported as								|
|  ---------------------------------------------------------- | --------------------------------------------|
|   Oncogenic	AND Likely oncogenic			|  Oncogenic/Likely oncogenic						|
|   Benign AND Likely beign				|  Benign/Likely benign							|
|   - Any oncogenic term AND Uncertain significance<br> - Any oncogenic term AND any benign term <br> - Uncertain significance AND any benign term			|  Conflicting classifications of oncogenicity.	<br> The conflicting terms and the number of submissions are provided. <br>	e.g. Oncogenic(1); Uncertain significance(1)			|