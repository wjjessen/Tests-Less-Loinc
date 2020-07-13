# Tests-Less-Loinc

Python notebook merging exports from CLS CT (joined with Analyte Explorer) and CLS LOINC on test number/zctestcode and visualized with a Venn diagram to verify.

SQL query for CLS CT joined with AE): 

select a.zctestcode, a.name, a.description, b.testableitemname, b.testmethodologydescription, b.qbsspecimendescription, 
        c.aeproductid, c.aespecimen, c.aemethodology from test a 
left join testtoaetestingdefinitionsuspense b on a.testid = b.testid 
left join aetestingdefinition c on a.containedbyaetestingdefinitionid = c.aetestingdefinitionid 
where a.name is not null;

