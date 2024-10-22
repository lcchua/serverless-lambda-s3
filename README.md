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

### Execution steps:

1. Check that Serverless Framework is installed
```bash
serverless --version
``` else,
```bash
npm nstall -g serverless
```
2. Next configure Serverless Framework with AWS credentials,
```bash
serverless config credentials --provider aws --key <AWS Access Key ID> --secret <AWS Secret Access Key> --profile serverlessUser
```
3. Run the Nodejs packages clean install,
```bash
npm ci
```
4. Update the `serverless.yml` file.

5. Deploy the Lambda function, `handler.js`,
```bash
serverless deploy -v
```
6. Test the Lambda function, by uploading the `sampleData.csv` file to S3 `lcchua-serverless-bucket-input` folder, and look into S3 `lcchua-serverless-bucket-output` folder for the resulting `sampleData.txt` file.

7. Perform clean-up actions.
```bash
npm uninstall -g serverless

rm -rf serverless-lambda-s3 (optional)

<Cleanup AWS resources by deleting the S3 bucket and Cloudformation stack>
```
