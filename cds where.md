<a name="top"></a>

# cds where

```ABAP
define view zsf_cds1 as select from ekpo
{
    key ebeln,
        ebelp,
        matnr
}where mandt = $session.client
 and aedat < $session.system_date

```
