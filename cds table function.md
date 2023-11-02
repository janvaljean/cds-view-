

<a name="top"></a>

#  cds table functions

- [define table function](#define table function)
  - [ make your class and methods -public and static](# make your class and methods -public and static)
  - [create your cds](#create your cds)



## define table function

Internal Tables ...


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
<p align="right"><a href="#top">⬆️ back to top</a></p>
