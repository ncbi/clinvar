# Review status 

## Submitted records (SCV)
Review status on submitted records (SCVs) with classifications of somatic clinical impact and oncogenicity will be the same as in the past:
|   Number of stars   |     Review status                       |     Description                                                                                                                             |   |   |
|------------------------------|----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|---|---|
|     four                     |     practice   guideline                     |     For variants   included in a practice guideline                                                                                              |   |   |
|     three                    |     reviewed by   expert panel               |     For variants   submitted by an expert panel                                                                                                  |   |   |
|     one                      |     criteria   provided, single submitter    |     For variants   submitted with a classification, assertion criteria, and evidence for the   classification (or a public contact)              |   |   |
|     zero                     |     no assertion   criteria provided         |     For variants submitted   with a classification but without assertion criteria and evidence for the   classification (or a public contact)    |   |   |
|     zero                     |     no classification  provided                  |     For variants   submitted without a classification                                                                                            |   |   |


## Review status for germline classification on aggregate records (VCV and RCV)

Review status for germline classification on VCV and RCV records will be calculated as in the past, namely:
1. if there is a submitted record from a practice guideline or an expert panel, the review status from the submitted record (SCV) is used for the VCV and RCV records
2. otherwise, the review status is based on
    * whether any submitted record provided assertion criteria and evidence for the classification (or a public contact) and
    * whether the submitted records agree on the classification

|     Number of   stars    |     Review status                                             |     Description                                                                                                                                                                                                                                                                       |   |   |
|--------------------------|---------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|---|
|     four                 |     practice   guideline                                      |     There is a   submitted record with a germline classification from a practice guideline.                                                                                                                                                                                           |   |   |
|     three                |     reviewed by   expert panel                                |     There is a   submitted record with a germline classification from an expert panel.                                                                                                                                                                                                |   |   |
|     two                  |     criteria   provided, multiple submitters, no conflicts    |     There are multiple   submitted records with a germline classification. Assertion criteria and   evidence for the classification (or a public contact) were provided and the   classifications agree.                                                                              |   |   |
|     one                  |     criteria   provided, conflicting classifications          |     There are multiple submitted records with a germline   classification. Assertion criteria and evidence for the classification (or a   public contact) were provided but there are conflicting classifications. The conflicting   values for the classification are enumerated.    |   |   |
|     one                  |     criteria   provided, single submitter                     |     There is a   single submitted record with a germline classification. Assertion criteria,   and evidence for the classification (or a public contact) were provided.                                                                                                               |   |   |
|     zero                 |     no assertion   criteria provided                          |     There is a   single submitted record with a germline classification but without assertion   criteria and evidence for the classification (or a public contact).                                                                                                                   |   |   |
|     zero                 |     no classification  provided                                   |     There are one   or more submitted records without a classification.                                                                                                                                                                                                               |   |   |
|     zero                 |     no classification for the single variant                 |     The variant   was not classified directly in any submitted record; it was submitted to   ClinVar only as part of a haplotype or a genotype.                                                                                                                                       |   |   |



## Review status for classification of oncogenicity on aggregate records (VCV and RCV)

Review status for classification of oncogenicity on VCV and RCV records will be calculated similar to germline classification, described above, except that we will look for agreement or conflicts in the oncogenicity classification.

## Review status for classification of somatic clinical impact on aggregate records (VCV and RCV)

Review status for classification of somatic clinical impact on VCV and RCV records will differ from germline and oncogenicity, in that we will not look for agreement or conflicts in the classification of clinical impact.

The rationale is that for a given variant, it will be typical for different tiers to be reported for different assertion types and different tumor types, so conflicts are not informative. 
So review status will be calculated as follows:
1. if there is a submitted record from a practice guideline or an expert panel, the review status from the submitted record (SCV) is used for the VCV and RCV records
2.  otherwise, the review status is based on whether any submitted record provided assertion criteria and evidence for the classification (or a public contact)

|     Number of   stars    |     Review status                               |     Description                                                                                                                                                                                  |   |   |
|--------------------------|-------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|---|
|     four                 |     practice   guideline                        |     There is a   submitted record with a somatic classification of clinical impact from a   practice guideline.                                                                                  |   |   |
|     three                |     reviewed by   expert panel                  |     There is a   submitted record with a somatic classification of clinical impact from an   expert panel.                                                                                       |   |   |
|     two                  |     criteria   provided, multiple submitters    |     There are multiple   submitted records with a somatic classification of clinical impact. Assertion   criteria and evidence for the classification (or a public contact) were   provided.     |   |   |
|     one                  |     criteria   provided, single submitter       |     There is a   single submitted record with a somatic classification of clinical impact. Assertion   criteria, and evidence for the classification (or a public contact) were   provided.      |   |   |
|     zero                 |     no assertion   criteria provided            |     There is a   single submitted record with a somatic classification of clinical impact but   without assertion criteria and evidence for the classification (or a public   contact).          |   |   |
|     zero                 |     no classification provided                  |     There are one   or more submitted records without a classification.                                                                                                                          |   |   |
|     zero                 |     no classification for the single variant    |     The variant   was not classified directly in any submitted record; it was submitted to   ClinVar only as part of a haplotype or a genotype.                                                  |   |   |




