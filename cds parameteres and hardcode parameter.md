<a name="top"></a>

# cds view with parameters and hardcode parameter
``` abap
define view zsf_cds_call 
with parameters p_mattype : mtart
as select from zsf_cds_input( p_mtype: $parameters.p_mattype, p_mgroup:'01'  )
{
    matnr,
    mtart,
    matkl,
    ntgew
}
```

