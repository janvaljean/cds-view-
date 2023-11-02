
<a name="top"></a>

#  cds table functions
 
  - [define table function](#define-table-function)
  - [make your class and methods public and static](#make-your-class-and-methods-public-and-static)
  - [create your cds](#create-your-cds)



## define table function


```CDS

@EndUserText.label: 'production orders'
define table function zsf_if_prod_orders
//with parameters parameter_name : parameter_type
returns {
  client : abap.clnt;
  prod_order : aufnr;
  order_type : auart;
  
}
implemented by method zsf_class_tf=>get_order_details;
```

## make your class and methods public and static


```ABAP
class zsf_class_tf definition public.

  public section.
  interfaces if_amdp_marker_hdb.
   class-methods get_order_details for table function zsf_if_prod_orders.

  protected section.
  private section.
endclass.



class zsf_class_tf implementation.
  method get_order_details by database function for hdb language
                            sqlscript options read-only using aufk.

     return select mandt as client, aufnr as prod_order, auart as order_type from aufk;

  endmethod.

endclass.
```
## create your cds


```CDS
define view zsf_cds_call_tf_Test as select from zsf_if_prod_orders
{
    prod_order,
    order_type
}

```
<p align="right"><a href="#top">⬆️ back to top</a></p>

<details>
  <summary>Expand to view the details</summary>
  <!-- -->

   CDS table function returns a tabular result set. This can be used (like every CDS entity) as a data source in other CDS entities or in Open SQL read statements. The prerequisite for use is that the specified AMDP function implementation exists and is active.

A CDS table function is in the namespace of the data types in ABAP Dictionary and of the global object types in the class library.

