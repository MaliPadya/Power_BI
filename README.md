# Master_Dashboard

### Dashboard Link : [Master Dashboard.pdf](https://github.com/MaliPadya/Power_BI/files/15475355/Master.Dashboard.pdf)

## Problem Statement

The VMS (Vendor Management System) Power BI dashboard provides managers with comprehensive insights into their VMS clients. It allows them to track various key metrics related to client requirements, candidate submissions, interviews, and offers. By visualizing this data, managers can make informed decisions and optimize their staffing processes effectively.


### Steps followed 

- Step 1 : Connect Data through Web.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present except column named "Arrival Delay".
- Step 5 : Create different types Relationships (Many To Many , Oane to Many)
- Step 6 : Created Vertual Date Column using "CalenderAuto" DAX
- Step 7 : used differend relationship for different calculation according to defined parameter using "USERELATIONSHI" Function
- Step 8 : create Ignore table if i want to ignore some entries
- Step 9 : Create Row Level security For Data Privacy

Snap of RLS ,

![image](https://github.com/MaliPadya/Power_BI/assets/170869800/ef19c2ce-2ebf-4ae1-9c67-bda3a1fbdaed)
        

Some Example of calculation
        
- Step 10 : New measure was created to find total count Closed Requirement.

Following DAX expression was written for the same,
        
        Closed = CALCULATE(COUNT('Job_Table'[JOB COMPANY]),'Job_Table'[JOB STATUS]="CLOSED")
        
A card visual was used to represent count of Closed_Jobs.

![image](https://github.com/MaliPadya/Power_BI/assets/170869800/c106b7c3-071a-4928-a0f0-18e6ecf49f3d)

        
 - Step 16 : New measure was created to find  Candidate Markup_%,
 
 Following DAX expression was written to find Candidate Markup_%,
 
         Candidate Markup % = Start_Ends[AGREED BILL RATE]/Start_Ends[AGREED PAY RATE]
 
 A card visual was used to represent this perecntage.
 
 
 ![image](https://github.com/MaliPadya/Power_BI/assets/170869800/4c933e84-2b33-4988-8cb4-2bb4ac04ee89)

 
 - Step 17 : New measure was created to calculate Jobs which are in 0 Subs.
 
 Following DAX expression was written to find count of 0 Sub Jobs,
 
         0 Sub positions = CALCULATE(COUNT('Job_Table'[JOB COMPANY]),'Job_Table'[First External Submittal Date]= BLANK(), 'Job_Table'[JOB STATUS] IN {"OPEN","ON HOLD"})
    
 A card visual was used to represent this Jobs which are in 0 Subs. 
 
 ![image](https://github.com/MaliPadya/Power_BI/assets/170869800/715f389d-75be-4b3b-9093-75555a16479b)
 



