### Module 3.7 Assignment by Chua Lai Chwang of CE7

To deploy a NodeJS Lambda function that responds to events in an S3 bucket using Serverless Framework

- Name of the Lambda Function: lcchua-processCSV<br>
- Name of the S3 bucket:<br>
     - lcchua-serverless-bucket-input
     - lcchua-serverless-bucket-output

The Lambda function responds to `.csv` files uploaded to an S3 bucket, transforms the data to a fixed width format, and writes the data to a `.txt` file in an output bucket. Fro example,

##### sampleInputData.csv

```
First,Last,Email,Phone
John,Munson,john.munson@gmail.com,343-231-3893
Ed,Karisch,edward.karisch@gmail.com,680-236-1187
Josh,Stevens,josh.stevens@gmail.com,851-990-4343
```

##### sampleOutputData.txt

```
John                Munson              john.munson@gmail.com                             343-231-3893
Ed                  Karisch             edward.karisch@gmail.com                          680-236-1187
Josh                Stevens             josh.stevens@gmail.com                            851-990-4343
```
