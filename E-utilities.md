## E-utilities


With the change in the format of our XML to support somatic classifications, efetch commands in E-utilities were updated to support both old and new formats at least through June 2024.

* The existing queries will return the new XML.
    e.g. this query will return XML in the new format for VCV000014206:
    https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=clinvar&rettype=vcv&id=VCV000014206
    e.g. this query will XML in the new format for RCV000000606:
    https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=clinvar&rettype=clinvarset&id=RCV000000606

* The old format for XML will be accessible by adding the parameter old_xml=T
    e.g. this query will return XML in the old format for VCV000014206:
    https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=clinvar&rettype=vcv&id=VCV000014206&old_xml=T
    e.g. e.g. this query will XML in the old format for RCV000000606:
    https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=clinvar&rettype=clinvarset&id=RCV000000606&old_xml=T
* So to continue using the old format until you can switch to the new format, just add the parameter old_xml=T to your queries.

