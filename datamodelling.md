## Data Modelling

### Dimension Fact Model

Dimensional modelling is data structure technique optimized for data storage in a data warehouse. The purpose of dimensional model is to optimize the database for fast retrieval
of data. The concept of Dimension modelling was developed by __Ralph kimball__ and consist of fact and dimension tables.

__A Dimensional model is designed to read, summarize, analyze numeric information like values, balances, counts, weights, etc. in a data warehouse. 
In contrast, relation models are optimized for addition, updating and deletion of data in a real-time Online Transaction System.__

These dimensional and relational models have their unique way of data storage that has specific advantages.

__For instance, in the relational mode, normalization and ER models reduce redundancy in data. On the contrary, dimensional model arranges data in such a way that it is 
easier to retrieve information and generate reports.__

Hence, Dimensional models are used in data warehouse systems and not a good fit for relational systems. 

### Elements of Dimensional Data Model

#### Fact

Facts are the measurements/metrics or facts from your business process. For a Sales business process, a measurement would be quarterly sales number

#### Dimension

Dimension provides the context surrounding a business process event. In simple terms, they give who, what, where of a fact. In the Sales business process, 
for the fact quarterly sales number, dimensions would be

* Who – Customer Names
* Where – Location
* What – Product Name

In other words, a dimension is a window to view information in the facts. 

Each row in a dimension have a surrogate which is generally a unique integer. It is declared as primary key. Natural key like other attribute of dimensions are not made primary
key as there value can change over time.

These surrogate keys are also stored in fact table as foreign keys to retrieve data from dimensions while creating reports or aggregating data based on dimension attributes.

Example - There is an pricing application for IBM HW products. Its data warehouse can contain fact related to quote level information. It can be associated to several 
dimensions like customer, exchange rate, user etc using foreign keys.

Mostly, dimension fact modelling ends up with kind of star schema or snowflake. 

#### Types of Dimension

##### Slowly Changing Dimension Techniques

1.__Type 0: Retain Original__ 
With slowly changing dimension type 0, the dimension attribute value never changes, so facts are always grouped by this original value. Type 0 is appropriate for any 
attribute labeled “original,” such as a customer’s original credit score or a durable identifier. It also applies to most attributes in a date dimension.

2.__Type 1: Overwrite__ 
With slowly changing dimension type 1, the old attribute value in the dimension row is overwritten with the new value; type 1 attributes always reflects the most recent 
assignment, and therefore this technique  destroys  history.  Although  this  approach  is  easy  to  implement  and  does  not  create additional dimension rows, you must be
careful that aggregate fact tables and OLAP cubes affected by this change are recomputed.

3.__Type 2: Add New Row__ 
Slowly  changing  dimension type  2 changes  add  a  new  row  in  the  dimension  with  the  updated attribute values. This requires generalizing the primary key of the
dimension beyond the natural or durable key because there will potentially be multiple rows describing each member. When a new row is created for a dimension member, a new 
primary surrogate key is assigned and used as a foreign key in all fact tables from the moment of the update until a subsequent change creates a new dimension key and 
updated dimension row. A minimum of three additional columns should be added to the dimension row with type 2 changes: 
1) row effective date or date/time stamp;  2) row expiration date or date/time stamp; and 3) current row indicator.

__Reference__
1. [Kimball group guide](http://www.kimballgroup.com/wp-content/uploads/2013/08/2013.09-Kimball-Dimensional-Modeling-Techniques11.pdf)
2. [Guru 99 dimension modelling overview](https://www.guru99.com/dimensional-model-data-warehouse.html)


## Star Schema & Snowflake Schema

The schemas are designed to address the unique needs of very large database for analytical purpose(OLAP). 
Types of Data Warehouse Schema:

Following are 3 chief types of multidimensional schemas each having its unique advantages.

* Star Schema
* Snowflake Schema
* Galaxy Schema

### Star Schema

Star schema is mutli-dimensional model used for data warehousing where there is one fact at the center of stars and dimensions are associated to it. It is called star schema
as it resembles a start structure. The star schema is the simplest type of Data Warehouse schema. It is also known as Star Join Schema and is optimized for querying large data sets.

In the following example,the fact table is at the center which contains keys to every dimension table like Dealer_ID, Model ID, Date_ID, Product_ID, Branch_ID & other attributes like Units sold and revenue.

![](https://github.com/BParesh89/bigdata-resources/blob/master/star.png)

__Characteristics of Star Schema__

* Every dimension in a star schema is represented with the only one-dimension table.
* The dimension table should contain the set of attributes.
* The dimension table is joined to the fact table using a foreign key.
* The dimension table are not joined to each other.
* Fact table would contain key and measure.
* The Star schema is easy to understand and provides optimal disk usage.
* The dimension tables are not normalized. For instance, in the above figure, Country_ID does not have Country lookup table as an OLTP design would have.
* The schema is widely supported by BI Tools.

### Snowflake schema

__SNOWFLAKE SCHEMA__ is a logical arrangement of tables in a multidimensional database such that the ER diagram resembles a snowflake shape. A Snowflake Schema is an extension of a Star Schema, and it adds additional dimensions. The dimension tables are normalized which splits data into additional tables.

In the following example, Country is further normalized into an individual table.

![](https://github.com/BParesh89/bigdata-resources/blob/master/snowflake.png)

__Characteristics of Snowflake Schema__

* The main benefit of the snowflake schema it uses smaller disk space.
* Easier to implement a dimension is added to the Schema
* Due to multiple tables query performance is reduced
* The primary challenge that you will face while using the snowflake Schema is that you need to perform more maintenance efforts because of the more lookup tables.

### Star Vs Snowflake Schema: Key Differences
|Star Schema	| Snow Flake Schema| 
| --- | --- |
| Hierarchies for the dimensions are stored in the dimensional table.| 	Hierarchies are divided into separate tables.|
| It contains a fact table surrounded by dimension tables.| One fact table surrounded by dimension table which are in turn surrounded by dimension table.|
| In a star schema, only single join creates the relationship between the fact table and any dimension tables.|	A snowflake schema requires many joins to fetch the data.|
| Simple DB Design.| Very Complex DB Design.|
| Denormalized Data structure and query also run faster.| Normalized Data Structure.|
| High level of Data redundancy. | Very low-level data redundancy.|
| Single Dimension table contains aggregated data. |	Data Split into different Dimension Tables.|
| Cube processing is faster.|	Cube processing might be slow because of the complex join.|
| Offers higher performing queries using Star Join Query Optimization. Tables may be connected with multiple dimensions.| The Snow Flake Schema is represented by centralized fact table which unlikely connected with multiple dimensions.|


### Galaxy Schema 

A GALAXY SCHEMA contains multiple fact table that share dimension tables between them. It is also called Fact Constellation Schema. The schema is viewed as a collection of stars hence the name Galaxy Schema. It is kind of combination of star and snowflake schema.

![](https://github.com/BParesh89/bigdata-resources/blob/master/snowflake.png)

In Galaxy schema shares dimensions are called Conformed Dimensions.

__Characteristics of Galaxy Schema__

* The dimensions in this schema are separated into separate dimensions based on the various levels of hierarchy.
* For example, if geography has four levels of hierarchy like region, country, state, and city then Galaxy schema should have four dimensions.
* Moreover, it is possible to build this type of schema by splitting the one-star schema into more Star schemes.
* The dimensions are large in this schema which is needed to build based on the levels of hierarchy.
* This schema is helpful for aggregating fact tables for better understanding.
