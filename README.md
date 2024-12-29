# Image Conversion and Resizing Lambda Function

This AWS Lambda function automatically converts images uploaded to a source S3 bucket into the WebP format, resizes them to a maximum dimension of 300x300 pixels, and stores the optimized image in a destination S3 bucket. The function is triggered by an `S3:ObjectCreated` event.

---

## Features

- Converts images to **WebP** format.
- Resizes images to fit within a maximum width and height of **300x300 pixels** while maintaining the aspect ratio.
- Compresses the output image with a configurable quality setting (default: 75).
- Uploads the processed image to a destination S3 bucket.

---

## Requirements

### Prerequisites

1. **AWS S3 Buckets**: 
   - A source bucket where images are uploaded.
   - A destination bucket for resized images (`<source-bucket-name>-resized`).

2. **Image Types Supported**: 
   - JPG
   - PNG

3. **Node.js Dependencies**:
   - `@aws-sdk/client-s3`: For interacting with S3.
   - `sharp`: For image conversion and resizing.
   - `util`: For event logging and debugging.
   - `stream`: For handling object streams.

---

## Setup Instructions

### 1. Install Dependencies
To ensure the Lambda function has access to the required libraries, install dependencies locally and package them with the Lambda code.

```bash
npm install @aws-sdk/client-s3 sharp


