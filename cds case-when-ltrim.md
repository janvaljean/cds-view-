<a name="top"></a>

# cds case-when-ltrim
    -[ltrim remove the 'T' from matnr of the left side]

```CDS
define view zsf_cds_session as select from ekpo
{
    key ebeln,
        ebelp,
        ltrim(matnr, 'T') as Material_Number,
        
        case statu
            when 'A' then 'Angebot vorhanden bei Anfrageposition'
            when 'F' then 'Über Fertigungsauftrag angelegt'
            else 'No Quotation'
        end as RFQ_Status,
        
        case
            when lgort = 'TM01' then 'STR1'
            when lgort = 'TM02' then 'STR2'
        
        end as STR_LOC        
        
}
 

```
