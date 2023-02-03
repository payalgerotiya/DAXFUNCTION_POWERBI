

14 DAX FUNCTION

1)AGGREGATE FUNCTION
     what will be the total amount 
        FORMULA: Total Amount = SUM(sales[Amount])
        
2) TOTAL BOX 
         FORMULA: Total boxes = SUM(sales[Boxes])
         
3) TOTAL SHIPMENTS 
    Shipments means: 1 row count as 1 Shipment 
     FORMULA: Shipment Count = COUNTROWS(sales)
     
 4) REUSABILITY
       Amount per Shipment = ([Total Amount]/[Shipment Count])       {Total Amount,Shipment Count:- REUSABLE}

  ANOTHER WAY TO CALCULATE " Amount per Shipment"
          Aps2 = SUM(sales[Amount])/COUNTROWS(sales)
          
  5) DIVIDE FUNCTION
           FORMULA: Amount per box = DIVIDE([Total Amount],[Total boxes],"No boxes")
  ANOTHER WAY
           Aps2 = SUM(sales[Amount])/COUNTROWS(sales)
           
  6) IF FUNCTION 
        FORMULA:  Aps target achieved? = IF([Aps2]>4800,"Yes","No")
   ANOTHER WAY    
        Aps target achieved2 = IF([Aps2]>4800,"🥇","👎")
   
 7) DISTINCTCOUNT FUNCTION
        How many different product on one person  
        FORMULA:  count of product = DISTINCTCOUNT(sales[Product])

8) CALCULATE
           FORMULA:  Shipment Count = COUNTROWS(sales)
                               Low Box Shipment Count = CALCULATE([Shipment Count],sales[Boxes]<50 )

9) FILTER
      FORMULA:   Bar Shipment = CALCULATE([Shipment Count],products[Category]="Bars")
                            Americas shipments = CALCULATE([ShipmenCount],locations[Region]="Americas")

10) ADD TABLE 
       FORMULA:   datamaster = CALENDAR(FIRSTDATE(sales[Date]) ,LASTDATE(sales[Date]))





11)  ADDING COLUMNS 
FORMULA:  year = YEAR(datamaster[Date])
                     month = MONTH(datamaster[Date])
                      Month Name = FORMAT(datamaster[Date],  "mmm")
                       week num = WEEKNUM(datamaster[Date])

12) ROW CONTEXT
      What is total amount from the friday sales 
       FORMULA: Friday Amount = CALCULATE([Total Amount],sales[Weekday]=6)

13) VARIABLES 
       FORMULA; NZAU Sales Amount = 
var naAmount =CALCULATE([Total Amount],locations[Geo] ="New Zealand") 
var auAmount =CALCULATE([Total Amount],locations[Geo] = "Australia")
return
naAmount + auAmount
  
14) OR FUNCTION
FORMULA: NZAUSales 2 = CALCULATE([Total Amount],locations[Geo]in {"New Zealand","Australia"})
           {Using IN FUNCTION you can check list of item }
        



