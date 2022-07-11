# Nowcasting Malaysia’s GDP with Machine Learning

### Introduction
This report presents the International Data Science Accelerator Programme's output for Nowcasting Malaysia's Gross Domestic Product (GDP) using Machine Learning. This mentor-mentee programme was held over the 12 weeks (April 11 to July 1 2022) between mentees, Veronica Jamilat, Khadijah Jasni, Fatin Ezzati (statisticians from the Department of Statistics Malaysia) and Will Malpass (Data Scientist, Data Science Campus UK) as a mentor.

This project aims to identify a new and potential approach to nowcasting GDP using Machine Learning models. This new approach may complement the existing method of producing GDP advanced estimates. The project output is reproducible and accessible through GitHub.

### Methodology Framework
![overall data science drawio (1)](https://user-images.githubusercontent.com/58675575/175923336-c3e4493c-2c31-4d1e-942b-1b4906893135.png)

### Data and Experimental Setup
The most crucial part of executing this project is acquiring relevant data series. Initially, we managed to compile a dataset comprising more than 100 economic-related variables at different time-frame. Some variables have more extended back series, while some indicators are only available in shorter time series, making the variable selection process consume much more time than expected. The process includes cross-checking available time-series data on different platforms and harmonising those datasets.

### Experimental Procedure
![Data Science drawio (1)](https://user-images.githubusercontent.com/58675575/175923387-729637b1-ab78-48a0-a97f-931253a9e8a3.png)

### Data
Before implementing Machine Learning Models, we have experimented with various combinations of a dataset. Those datasets are selected with variables that have extended back series and transformed into a stationary dataset. 

| Variable | Description |
| ------------- | ------------- |
| CPI  | Consumer Price Index |
| CIC  | Coincident Index (CI) Composite Index  |
|WSTIVO | WST Index (Volume) |
|IPIELEC | IPI: Electricity |
|WRTSICE	|474: Retail Sale of Information and Communication Equipment in Specialised Stores|
|WRTS	|WRT|
|EXSITC0|	Exports: Food|
|WRTSGRG	|476: Retail Sale of Cultural and Recreation Goods in Specialised Stores|
|LOANBS	|Total Loans in Banking System 1.18|
|MDTS|	Monthly Distributive Trade|
|WSTSHHG|	464: Wholesale of Household Goods|
|FIIXE|	Fixed Deposits as at. 1.25.2
|WRTSAF|	473 : Retail Sale of Automotive Fuel in Specialised Stores
|WRTSOG|	477: Retail Sale of Other Goods in Specialied Stores
|LOANCB|	Total Loan Banking System (Fixed and Savings Deposits) 
|IMSITC8|	Imports: Miscellaneous Manufactured Articles
|IPIMFG|	IPI: Manufacturing
|LGC|	Lagging Index (LG) Composite Index
|WRTSOHE|	475: Retail Sale of Other Household Equipment in Specialised Stores
|IPITOT|	IPI: Total
|DEPBANKSYS|	Total Deposits Banking System (Fixed and Savings Deposits) 1.24
|FIXEIB|	Total Fixed Deposits Islamic Bank as at.
|MSM2|	Money Supply: M2
|MSM3|	Money Supply: M3
|IMSITC5|	Imports: Chemicals
|LOANIB|	Total Loans Islamic Bank as at.
|QCS|	Nilai Kerja Pembinaan
|WRTSNSS|	471: Retail Sale in Non-Specialised Stores
|IMSITC0|	Imports: Food
|DEPOIB|	Total Deposits Islamic Bank as at.
|IMTOT|	Imports: Total
|EXSITC5|	Exports: Chemicals
|WSTSFNB|	463: Wholesale of Food, Beverages and Tobacco
|WRTSFNB|	472: Retail Sale of Food, Beverages and Tobacco in Specialised Stores
|MSM1|	Money Supply: M1
|LIC|	Leading Index (LI) Composite Index
|WSTSFEE|	461: Wholesale on a Fee or Contract Basis
|FIXECB|	Total Fixed Deposits Comm Banks as at.
|EXTOT|	Exports: Total
|IMSITC6|	Imports: Manufactured Goods
|SWIPRO|	Swine_Production
|EXSITC6|	Exports: Manufactured Goods
|EXSITC8|	Exports: Miscellaneous Manufactured Articles
|WSTSMES|	465: Wholesale of Machinery, Equipment and Supplies
|RIVA|	Retail Index (Value)
|RIVO|	Retail Index (Volume)
|AFRIB|	Average Financing Rate Islamic Bank 2.2
|DEPOIB2|	Total Deposits Islamic Bank as at.
|IMSITC7|	Imports: Machinery & Transport Equipment
|IMSITC2|	Imports: Crude Materials, Inedible
|SLMFG|	SALES-Manufacturing sector
|SLENE|	SALES-Electrical and Electronic
|SAVDEP|	Savings Deposits as at. 1.25.2
|IMSITC3|	Imports: Mineral Fuels, Lubricants, Etc.
|SLTEX|	SALES-Textiles, wearing apparel, leather products and footwear
|EXSITC7|	Exports: Machinery & Transport Equipment
|FOSWPRO|	Forestry_Sarawak
|SLWOOD|	SALES-Wood products, furniture, paper products, printing and publishing
|EXSITC2|	Exports: Crude Materials, Inedible
|ALRCB|	Average Lending Rate Commercial  Banks 2.1
|FOSBPRO|	Forestry_Sabah
|FOLOPRO|	Forestry_Production of Log 
|WSTSAGRI|	462: Wholesale of Agricultural Raw Materials and Livestock
|SDRIB|	Saving Deposits Interest Rate Islamic Bank 2.2
|SLTRA|	SALES-Transport Equipment and Other Manufactures
|LOANMB|	Total Loans Merchant Banks as at.
|SLNMET|	SALES-Non-metallic mineral products, basic metal and fabricated metal products
|IMSITC1|	Imports: Beverages And Tobacco
|CEMENT|	Cement Price 
|FIAQUA|	Fishery_Kuantiti Pengeluaran Akuakultur 
|WMVSMRM|	452: Maintenance and repair of motor vehicles
|USDEXC|	USD Exchange rate
|SLPET|	SALES-Petroleum, chemical, rubber and plastic products
|EXSITC3|	Exports: Mineral Fuels, Lubricants, Etc.
|WMVSMVA|	453: Sale of motor vehicle parts and accessories
|PPID|	PPI: Electricity and gas
|EXSITC1|	Exports: Beverages And Tobacco
|JOBCREATE|	Job Openings
|WMVSMR|	454: Sale, maintenance and repair of motorcycles and related parts and accessories
|UERATE|	Unemployment Rate
|PPITOT|	PPI: Total
|MVIVA|	Motor Vehicle Index (Value)
|IMSITC4|	Imports: Animal And Vegetable Oils And Fats
|PPIB|	PPI: Mining 
|EXSITC4|	Exports: Animal And Vegetable Oils And Fats
|CRUDEBRUSD|	Crude oil, Brent
|IMSITC9|	Imports: Miscellaneous Transactions And Commodities
|PPIC|	PPI: Manufacturing
|IOSADMIN|	IoS-Administrative & Support Services
|IOSOTHER|	IoS-Other Private Services
|BFBLRIB|	Based Financing Rate (BLR) Islamic Banks 2.2
|BLBLRCB|	Based Lending Rate (BLR) Comm Banks 2.1
|PPIE|	PPI: Water supply
|EXSITC9|	Exports: Miscellaneous Transactions And Commodities
|PPIA|	PPI: Agriculture, forestry and fishing
|TOURIST|	Tourist Arrivals
|IPIMIN|	IPI: Mining
|IOSTOT|	IoS-Total
|GDPGR|	GDP Growth Rate

