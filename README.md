# Retail  sales forecast

## Scenario 

In this Lab  

Part 1:  We  will complete  the process of building and using a  **time-series** analysis  to forecast future sales from historical sales data , and than use of [PySpark](https://spark.apache.org/docs/latest/api/python/index.html) within [Apache Spark in Azure HDInsight](https://docs.microsoft.com/en-us/azure/hdinsight/spark/apache-spark-overview) environment to explore  data, transform the data into meaningful features ,build a **Random Forest Regression** model, and utilize the model to predict  next month’s sales numbers.


Part2 : In this tutorial, you learn how to use Microsoft **Power BI** to visualize data in an Apache Spark cluster in **Azure HDInsight** , make get insights from analyzing data to make business decisions more effective.


## Prerequisite

> To have Microsoft Account or a work or school account

> Install Power BI Desktop(windows OS)


## Create  Blob storage as container

Sign in to the Azure portal ,and in the upper-left corner of Azure portal, select **Storage Accounts**

<p align="center">
    <img src="images/007.png" width="20%" height="50%">

2. Select your **Storage Account**, if you have not **Storage Account**, create new

<img src="images/011.png" width="80%" height="80%">
<p align="center">
    

3. Click **Container**

<img src="images/008.png" width="80%" height="80%">

4. Click **add Container**

<img src="images/009.png" width="80%" height="80%">



* Name: **your unique name**
* Public access level : **Container**

<img src="images/010.png" width="80%" height="80%">

5. Click **OK**

## Upload datasets to Blob storage as container

1. Enter  already Created Storage Container

2. Click Upload

<img src="images/012.png" width="80%" height="80%">

3. Upload  datasets to Blob storage from your Computer folder

<img src="images/013.png" width="80%" height="80%">

## Create HDinsight cluster 

1-0. Use the search bar to find **HDinsight cluster**,and click Select.

1-1. In the **HDinsight cluster** workspace pane, select Create to begin.

 <img src="images/001.png" width="80%" height="80%">


1-2 Inpute and select data
* For Subscripition, Select your Subscripition

* For Resource group , Select your Resource group ,if not have any, Please click Create New

*  For cluster name, type a Unique Name

* For Region , Seclect **East US**

* For Cluster type , Select `Spark`

 <img src="images/002.png" width="50%" height="50%">

* For Cluster login password , Type a Unique password 

<img src="images/003.png" width="80%" height="80%">


1-3. In the **Storage pane** 

* For Primary Storage type , Select **Azure Storage**

* For Primary Storage account , Select **your storage accounts**

<img src="images/004.png" width="80%" height="80%">

1-4. In the **Configuration + pricing pane**

*  For Work Node , Select `D12 v2(4Cores,28GM) ` 
*  For Node type , modify number of node as `2` 

<img src="images/005.png" width="80%" height="80%">

1-5. Click Create 

<img src="images/06.png" width="80%" height="80%">

## upload code file to  Payspark  development enviroment

Wate for about 45min - 1hr , Service build complete .

1. On Cluster dashboards , Select **Jupyter notebook**

    <img src="images/015.png" width="50%" height="80%">

2. Inpute informations
* UserName: `admin`
* Passwords: you set passwords 

    <img src="images/014.png" width="50%" height="80%">

3. Upload `retail-sales-forecast.ipynb` , and then click upload 

    <img src="images/016.png" width="50%" height="80%">


4. Click **file**

    <img src="images/017.png" width="80%" height="80%">


## Data analysis and build model 

Detail train processing from [Model Train Processing](model/README.md)

### Prediction of Future Sales

1. Sorting the results by the ID and then removing all of the features to leave us with an ID and a predicted sales count

    <img src="images/043.png" width="80%" height="80%">

### Run queries on the dataframe

1. Once the table is created, you can run an interactive query on the data.

    <img src="images/042.png" width="80%" height="80%">









## Data Visualize by Power BI

1. Open Power BI Desktop


2. From the Home tab, navigate to Get Data > More...

    <img src="images/038.png" width="80%" height="80%">

3. Enter Spark in the search box, select Azure HDInsight Spark, and then select Connect.

    <img src="images/039.png" width="80%" height="80%">


4. Enter your cluster URL  in the Server text box 

    <img src="images/040.png" width="80%" height="80%">

5. Under Data connectivity mode, select DirectQuery. Then select OK

    <img src="images/041.png" width="80%" height="80%">

6. Enter the HDInsight login account information, then select Connect. The default account name is `admin`.



7. Select the `predictedSales` table, wait to see a preview of the data, and then select Load.

    <img src="images/044.png" width="80%" height="80%">

8. Sales distributed with **ID** and  **Price**

* Convert to a line chart by selecting the line chart template from the Visualizations pane.

    <img src="images/049.png" width="80%" height="80%">



    <img src="images/045.png" width="80%" height="80%">


9. Sales count 

* Convert to a line chart by selecting the line chart template from the Visualizations pane


    <img src="images/050.png" width="80%" height="80%">

    
    
    <img src="images/046.png" width="80%" height="80%">

10. Train sales distributed with **Item_ID** and  **Itemn_Price**

    <img src="images/049.png" width="80%" height="80%">

    <img src="images/048.png" width="80%" height="80%">

##  Conclusion

Congratulations! You now have learned how to:

1. Create Blob storage as container

2. Upload datasets to cloud storage

3. Create HDinsight cluster 

5. Use Spark API to train and predict model

6. Use  SQL language query dataframe

7. Make result value  to visualize  by Power BI

## Clean up Resource


In the resource group,Delete resource

1. HDinsight cluster

2. Azure Storage








