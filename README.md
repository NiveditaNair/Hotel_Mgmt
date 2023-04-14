# Hotel_Mgmt
Adhoc SQL Queries for performing Hotel management

Holiday Pickup Data serves as a way to pul and import raw data, which can be further engineered for analytical purposes, and if required, to be able to build an ML model for Active Hotel availability.

The queries in Holiday Pickup data extracts raw data based on a given information such as business start and end dataes (Primarily serve as Date ranges for subset extraction), Pickup start and end date.

This data is pulled from databases containing marketview data and pickup reports. The query performs the required calculations on a temporary table that stores the pulled raw data. This analysis is restricted only for active hotels, which are filtered out by an active flag (IsActive)

The Metrics Adhoc query file 

<Documentation Purpose> 
--> The input being passed is a set of date ranges and based on the parameter required to be filtered out, the input parameters can be the following (Occ Pivot, ADR pivot, RevPAR Pivot, Sort based on class, Sort based on market).
-->We are calculating the occupancy as (Total No. Of Rooms Sold/ Total No.of Availabe rooms), RevPAR as (Total Revenue/ Total No.Of Available Rooms), ADR as (Total Revenue/ Total No. Of Rooms Sold) for the data being pulled.
--> We are creating a pivot table in Excel and so writing code accordingly
--> Based on the requiredment we are also required to sort the data based on Class and Market.
--> During the sorting if there are null values for a partivular class or market they are not taken into account.
  
  <Documentation Purpose>

--> Once the raw data has been loaded into a temp table, a back up of the temp table is created in order to clean up the data and check for discrepencies such as occupancy greater than 100.
-->Once the descrepencies have been addressed we fill in the holes considering the data in hand to be split into data points (0-7 days,14 days, 21 days, 28 days).
--> we fill in the holes based on the data points.
--> once these holes are filled in, the cleaned data is inserted into the temp table and the backup table is destroyed. 
