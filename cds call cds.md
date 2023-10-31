<a name="top"></a>

# cds view with parameteres
``` abap
define view zsf_cds_call as select from zsf_cds_input( p_mtype:'ERSA', p_mgroup:'01'  )
{
    matnr,
    mtart,
    matkl,
    ntgew
}

    
```
