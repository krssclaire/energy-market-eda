# Electricity Price Behavior in Italy: A Data Analysis for Trading Insights

## 1. Overview and Project Aim
This project is intended to:
* Analyze energy prices dynamic in Italy
* Identify seasonal pattern and volatility
* Analyze the relationship between demand and supply  

*Technical tools*: This project will be developed entirely on Python programming language run on Jupyter Notebooks. 

## 2. Dataset
### Dataset Description
Due to the aim of analyzing prices related to the demand and the supply of the energy stock, it has been decided to analyze a period of time that goes from 01-01-2021 to 31-12-2025, in order to analyze long-term volatility, patterns and find helpful insghts for trading decision making.  
For this reason, despite energy prices are transmitted on quartely basis from 2025 ([ARERA Deliberation 304/2024/R/eel and TIDE – Testo Integrato del Dispacciamento Elettrico](https://confindustriatoscanacentroecosta.it/mercato-elettrico-il-prezzo-pun-diventa-quartorario-effetti-per-le-imprese/)), this project takes into consideration prices of PUN (Prezzo Unico Nazionale) index GME on hourly basis in order to analyze standardized data over time, in spite of detailed quartely frequency insights.  

The dataset is composed by downloaded data from two sources: 
1. The first one is GME ([Gestore del Mercato Elettrico]((https://www.mercatoelettrico.org/it-it/Home/Esiti/Elettricita/MGP/Esiti/PUN))) which is the official Italian energy market data provider, and official trading market.  
The dataset contains 5 tables(*), each one in an .xlsx file. Each table contains data of 1 year from Jenuary 1st to December 31st and it's composed by the following columns:
    * _Data_ - it's the date, formatted as dd/mm/yy in ascending order;
    * _Ora_ - it's the hour of the day, data type is integer that goes from 1 to 24;
    * _€/MWh_ - data type is float and it represent the price of the energy at that hour of the day by Mega Watt per hour. 
2. The second one is [TERNA Downolad Data Center](https://dati.terna.it/en/download-center). TERNA (Trasmissione Elettrica Rete Nazionale) is an Italian corporate operating in energy transmission nets.  
The dataset(*) is divided in two macro-areas:  
    1. Generation - it represents the  quantity of energy generated and in this study it describes the supply (S) of the energy.  
    The dataset is composed by 5 files (and tables), each one for each year and the columns contained are:
        * _Date_ - date format is <code>dd/mm/yy hh:mm:ss</code> on quarter basis;
        * _Actual Generation_ - datatype is float, the standard measure is not defined but it is assumed to be Mega Watt (MW);
        * _Primary Source_ - it represents the source of energy production and the values are Thermal_, _Wind_, _Geothermal_, _Photovoltaic_, _Self-consuption_, _Hydro_.
    2. Load - it represents the quantity of energy dispatched, for this study it's the demand (D) of the energy.
    The dataset is composed by 5 files (and tables), one for each year. The columns are:
        * _Date_ - date format is <code>dd/mm/yy hh:mm:ss</code> on quarter basis;
        * _Total Load [MW]_ - float data type
        * _Forecast Total Load [MW]_ - for this analysis will not be taken into consideration
        * _Bidding Zone_ - it would be helpful for zonal analysis and internal energy market dynamic. The zones, classified by energy transmission net prerequisites and characetristics,  are _Calabria_, _Centre-North_, _Centre-South_, _North_, _Sardinia_, _Sicily_, _South_, _Italy_.   

> (*) The name of each file (and so table) is formatted as follows:
> * For GME dataset is <code>GME-PUNi-202n.xlsx</code>;
> * For TERNA dataset the generation data is contained in <code>TERNA-gen-202n.xlsx</code> while the load data is in <code>TERNA-load-202n.xlsx </code>  
> where n goes from 1 to 5 in order to represent the five-year-period

## 3. Data cleaning
