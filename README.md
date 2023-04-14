# Hotel_Mgmt
Adhoc SQL Queries for performing Preformance management for hotel industry to help identify areas of growth, such as potential staffing needs. It helps to automate workflow by providing critial data points and its subsequent cross-functional performance metrics. 

Holiday Pickup Data serves as a way to pul and import raw data, which can be further engineered for analytical purposes, and if required, to be able to build an ML model for Active Hotel availability.

The queries in Holiday Pickup data extracts raw data based on a given information such as business start and end dataes (Primarily serve as Date ranges for subset extraction), Pickup start and end date.

This data is pulled from databases containing marketview data and pickup reports. The query performs the required calculations on a temporary table that stores the pulled raw data. This analysis is restricted only for active hotels, which are filtered out by an active flag (IsActive)

The Metrics Adhoc query file takes a date range input for filtering,with criteria such as Class and Market,  along with other requirement specific information, with the objective to calculate the occupancy as (Total No. Of Rooms Sold/ Total No.of Availabe rooms), RevPAR as (Total Revenue/ Total No.Of Available Rooms), ADR as (Total Revenue/ Total No. Of Rooms Sold) for the data being pulled. This data is then exported to ecel and subsequent pibot tables are created. The query also automates the task of filling null values

The HOLESFILLING query set filles incomplete datapoints with a certain criteria in mind (0-7 days,14 days, 21 days, 28 days) in case of conditions such as occupany of hotel rooms exceeding 100, to say the least. The newly freated information is stored in a backup table and the temporary table is deleted. 
