# Informatica Demo

Hello to anyone reading this from Texas Children's Hospital! Anyone else may be in the wrong place.

This is a record of my completion of the [Cloud Data Integration for Developers](https://now.informatica.com/Cloud-Data-Integration-for-Developers-onDemand.html) course in Informatica's online training materials.

## Experience

In support of completing the course, students must configure:
- A local SQL Server instance
- A Salesforce account
- A [Postman](https://www.postman.com) account (for REST API calls)
- An [OpenWeather](https://openweathermap.org/api) account

Thanks to my degree program and experience with Levrum Data Technologies, I had already done all of these except for Salesforce.

My Postman [environment](https://github.com/MHValdez/Informatica-Demo/blob/main/Informatica.postman_environment.json) and [collection](https://github.com/MHValdez/Informatica-Demo/blob/main/Informatica.postman_collection.json) for Informatica Cloud API calls are included in this repo. (Yes, the environment file contains my Informatica trial account password in plain text. With it present, you can run the requests in Postman to confirm I know what I'm doing.)

## Course Content

The course covers the following topics, as detailed in the [lab guide](https://github.com/MHValdez/Informatica-Demo/blob/main/fbc65587-3e77-4124-a057-a7f0b4d8e435_Cloud_Data_Integration_for_Developers_R42___onDemand_Lab_Guide__CDI_R42_DEV_OD_202308_.pdf):

### Administration
- Runtime Environment Configuration (Secure Agent)
- Connection Configuration
  - Microsoft SQL Server
  - CSV flat files
  - Web services (e.g., Salesforce)
- Source and Target Configuration

### Data Integration
- Replication
- Synchronization
- Data Transfer
- Filters
- Expressions
- Joiners
- Mapping
- Mapplets
- Taskflows
- Masking
- Parameterization
- REST API Usage
  - Interfacing with external APIs
  - Initiating tasks
  - Monitoring tasks
  - Retrieving task logs

## Issues

While I was able to complete all course content, there were several issues I encountered. I documented them and submitted them in my post-completion feedback. I've included them here.

### Content:

#### Module 11:
- A Check your Knowledge question states, "Which of the following load types always perform an incremental load in Replication Task?" This question has the wrong response marked correct. It should be "Incremental loads after initial partial load".


### Labs:

#### 0-3:
- This should have a note about expected datatypes for all columns. Many items that had automatically resolved to int type in my SQL Server wizard were expected to be string type by the labs.
- There should also be an explicit instruction to import the CUSTOMER_MASTER flat file.

#### 3-4:
- The included syntax for extracting a first name from Full_Name (page 68) returned an empty string to Salesforce in most cases for me. In a few cases, it worked correctly. To make it work consistently, I had to change it.


#### 3-6:
- The target connection on page 81 is CDI_SQL_Src and the target object is CUSTOMER_MASTER. As noted above, the student has never created a CUSTOMER_MASTER entity in any database at this point. The connection does not contain the target object when the student starts the lab.
- The source object on page 86 is UPDATE_CUSTOMERS.CSV. This file is not included in the lab prep files. The student has to fabricate the file to complete the lab as intended.


#### 6-1:
- The second screenshot for step 32 on page 100 has an orange highlight box around "Incoming Fields" despite "Join Condition" being selected.

#### 12-2:
- Attempting to use the masking techniques requested by the lab (page 238) results in the message: "This masking technique is not available in the trial version. Purchase a license to enable this masking technique." The only techniques available to trial accounts are Name and US ZIP Code.


![Screenshot 2024-02-07 194941](https://github.com/MHValdez/Informatica-Demo/assets/14323612/a4b97232-72e8-4076-b899-2fd08437d8e4)

*An outer join mapping from a two CSVs*
