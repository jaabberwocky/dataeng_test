# DSAID Data Engineering Technical Test

This test is split into 3 sections, **data pipelines**, **databases** and **system design**. 

## Submission Guidelines
Please create a Github repository containing your submission and send us an email containing a link to the repository.

Dos:
- Frequent commits
- Descriptive commit messages
- Clear documentation
- Comments in your code

Donts:
- Only one commit containing all the files
- Submitting a zip file
- Sparse or absent documentation
- Code which is hard to read

## Section 1: Data Pipelines
The objective of this section is to design and implement a solution to process a data file on a regular interval (e.g. daily). Given the test data file `dataset.csv`, design a solution to process the file, along with the scheduling component. The expected output of the processing task is a CSV file including a header containing the field names.

You can use common scheduling solutions such as `cron` or `airflow` to implement the scheduling component. You may assume that the data file will be available at 1am everyday. Please provide documentation (a markdown file will help) to explain your solution.

Processing tasks:
- Split the `name` field into `first_name`, and `last_name`
- Remove any zeros prepended to the `price` field
- Delete any rows which do not have a `name`
- Create a new field named `above_100`, which is `true` if the price is strictly greater than 100

*Note: please submit the processed dataset too.*

## Section 2: Databases
You are appointed by a car dealership to create their database infrastructure. There is only one store. In each business day, cars are being sold by a team of salespersons. Each transaction would contain information on the date and time of transaction, customer transacted with, and the car that was sold. 

The following are known:
- Both used and new cars are sold.
- Each car can only be sold by one salesperson.
- There are multiple manufacturers’ cars sold.
- Each car has the following characteristics:
- Manufacturer
- Model name
- Model variant
- Serial number
- Weight
- Engine cubic capacity
- Price

Each sale transaction contains the following information:
- Customer Name
- Customer Phone
- Salesperson
- Characteristics of car sold

Set up a PostgreSQL database using the base `docker` image [here](https://hub.docker.com/_/postgres) given the above. We expect at least a `Dockerfile` which will stand up your database with the DDL statements to create the necessary tables. Produce entity-relationship diagrams as necessary to illustrate your design.

## Section 3: System Design
You are designing data infrastructure on the cloud for a company whose main business is in processing images. 

The company has a web application which collects images uploaded by customers. The company also has a separate web application which provides a stream of images using a Kafka stream. The company’s software engineers have already some code written to process the images. The company  would like to save processed images for a minimum of 7 days for archival purposes. Ideally, the company would also want to be able to have some Business Intelligence (BI) on key statistics including number and type of images processed, and by which customers.

Produce a system architecture diagram (e.g. Visio, Powerpoint) using any of the commercial cloud providers' ecosystem to explain your design. Please also indicate clearly if you have made any assumptions at any point.


