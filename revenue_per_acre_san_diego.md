# San Diego County: Tax Revenue Per Acre

These represent the tax revenue (tax rate * property assessment value) per acre
of each urban parcel.  Tax rates are determined on a parcel-by-parcel basis by
joining the parcel data together with [Tax Rate Area (TRA) data](https://www.sandiegocounty.gov/content/dam/sdc/auditor/trb2021/tralist.pdf).

## Cleanup Steps

* Include only "taxable" parcels.  This means only parcels with "TAXSTAT"='T', and ones which belong to an existing TRA.
  * This has a side-effect of excluding all publicly owned parcels which contain things like public schools, public parks, post offices, etc.
* Include only "developed" parcels.  I'm loosely defining developed parcels as one which aren't just desert.
* Spread the land area shared by HOA parcels amongst all the HOA parcels.  In
  other words, take all the private land area shared between HOA members (e.g.
  HOA parks, HOA tennis courts, HOA pools, etc.), divide that area by the number
  of HOA parcels, then include that in the denominator of the revenue-per-acre
  analysis for each one.  This is necessary, otherwise HOA houses are
  significantly over-valued as tax revenue producers.

## Issues

There are still deficiencies in my processing steps, as well as missing data
from the source.  Some of these issues include, but are not limited to:

* Several parcels share identical geometries when the owner is leasing
  subdivisions of the parcel to other entities (e.g. UCSD leasing a lot on
  campus to Target), which currently show up as zero (black color).
* Several groupings of HOA parcels have a missing parcel which corresponds to
  the land shared by HOA members, which prevents my HOA cleanup step described
  above from working properly.  These parcels remain over-valued.
* Often a Walmart or other big box store will be represented by a single parcel
  including both the store and the corresponding parking lot.  However, In some
  cases, the two parcels are distinct, which makes the big box store appear
  significantly over-valued because the adjacent parking lot is not taken into
  consideration.  This is a non-trivial problem to solve because often there is
  no clue in the data which can help to automatically correlate the big box store
  with the parking lot.

## Plots

![Tax Revenue Per Acre in CB](renders/revenue_per_acre_CB.jpg)
![Tax Revenue Per Acre in CO](renders/revenue_per_acre_CO.jpg)
![Tax Revenue Per Acre in CV_denser_suburb](renders/revenue_per_acre_CV_denser_suburb.jpg)
![Tax Revenue Per Acre in CV](renders/revenue_per_acre_CV.jpg)
![Tax Revenue Per Acre in CV_west](renders/revenue_per_acre_CV_west.jpg)
![Tax Revenue Per Acre in DM](renders/revenue_per_acre_DM.jpg)
![Tax Revenue Per Acre in EC](renders/revenue_per_acre_EC.jpg)
![Tax Revenue Per Acre in EN](renders/revenue_per_acre_EN.jpg)
![Tax Revenue Per Acre in ES](renders/revenue_per_acre_ES.jpg)
![Tax Revenue Per Acre in IB](renders/revenue_per_acre_IB.jpg)
![Tax Revenue Per Acre in LG](renders/revenue_per_acre_LG.jpg)
![Tax Revenue Per Acre in LM](renders/revenue_per_acre_LM.jpg)
![Tax Revenue Per Acre in NC](renders/revenue_per_acre_NC.jpg)
![Tax Revenue Per Acre in OC](renders/revenue_per_acre_OC.jpg)
![Tax Revenue Per Acre in PW](renders/revenue_per_acre_PW.jpg)
![Tax Revenue Per Acre in SD](renders/revenue_per_acre_SD.jpg)
![Tax Revenue Per Acre in SM](renders/revenue_per_acre_SM.jpg)
![Tax Revenue Per Acre in SO](renders/revenue_per_acre_SO.jpg)
![Tax Revenue Per Acre in ST](renders/revenue_per_acre_ST.jpg)
![Tax Revenue Per Acre in VS](renders/revenue_per_acre_VS.jpg)
