This is a port of trhr/aws-transcribe-transcript intended to automate an AWS Lambda function creation with Cloudformation

# aws-transcribe-transcript
This is a simple utility script to convert the Amazon Transcribe .json transcript into a more readable transcript.

Amazon has a neat Transcription service and you can have the service identify speakers. And in their web interface, they show you a neat play-by-play transcript, but it's limited to the first 5,000 characters. If you want the full transcript, you have to download their JSON file. However, the JSON file only has the transcript as a big block and then some structured data below for the various speakers, start times, and text fragments.


## Cloudformation Directions
1. Upload the Cloudformation yaml file to create a Cloudformation Stack
2. Create an input/ folder in the S3 bucket that has been created by the stack
3. Upload the Amazon Transcribe's JSON file in th S3/input folder
4. Navigate back to the S3 bucket and a /output folder should have been created with the human-readable text file within
5. Download the human-readable transcript text file

## Cloudformation Clean-up
1. Empty S3 Bucket 
2. Delete Cloudforamtion Stack


The Cloudformation code has been adapted from LukasMusebrink https://www.itonaut.com/2018/10/03/implement-s3-bucket-lambda-triggers-in-aws-cloudformation/

The Python script for the lambda function was written by trhr https://github.com/trhr/aws-transcribe-transcript
