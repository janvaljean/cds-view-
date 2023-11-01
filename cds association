<a name="top"></a>

# cds association
    -JOIN on demand
    -make associations public 
    -association should be in entity list.
    -dont create association between the  different associations.
  

```CDS
define view zsf_cds_associations as select from vbak as _sheader
association [1..1] to vbap as _sitem on _sheader.vbeln = _sitem.vbeln
association [1..*] to I_BillingDocumentItem as _billing on _sheader.vbeln = _billing.SalesDocument
//association [1..*] to I_Material as _material on _sitem.matnr = _material.Material
association [1] to I_Customer as _custumer on _sheader.kunnr = _custumer.Customer 

{
    key _sheader.vbeln,
        _sheader.vbtyp,
       _sheader.kunnr as customer,
        
        //assocation as public  
        _sitem,
        _billing,
        _custumer
}
 
        
}
 

```
