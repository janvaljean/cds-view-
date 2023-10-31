<a name="top"></a>

# cds input


```ABAP
define view zsf_cds_input
    with parameters p_mtype : mtart, p_mgroup : matkl
 as select from mara
{
    key matnr,
        mtart,
        matkl,
        ntgew
}where mtart = :p_mtype
   and matkl = :p_mgroup

```
