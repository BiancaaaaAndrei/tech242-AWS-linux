# Hosting Static Websites on Amazon S3

- [Hosting Static Websites on Amazon S3](#hosting-static-websites-on-amazon-s3)
  - [URL Structure for S3 Website Endpoints](#url-structure-for-s3-website-endpoints)
- [Enabling S3 Bucket for Website Hosting](#enabling-s3-bucket-for-website-hosting)
  - [Example Result](#example-result)
  - [Important Note](#important-note)

Amazon S3 provides a straightforward way to host static websites, making them accessible on the internet. The website's URL depends on the AWS region where the S3 bucket is created.

## URL Structure for S3 Website Endpoints

The URLs for hosting static websites on S3 are based on the AWS region. There are two variations:

1. **Using Dash (`-`):**
   - Example: `http://<bucket-name>.s3-website-<AWS-region>.amazonaws.com`

2. **Using Dot (`.`):**
   - Example: `http://<bucket-name>.s3-website.<AWS-region>.amazonaws.com`

While the dash and dot URLs look similar, the choice depends on the specific AWS region.

# Enabling S3 Bucket for Website Hosting

To enable an S3 bucket for website hosting, follow these steps:

1. **Upload Website Content:**
   - Upload the necessary files (e.g., HTML, images) to the S3 bucket.

2. **Configure Bucket for Website Hosting:**
   - Navigate to the S3 bucket properties.
   - Scroll down and find the "Static website hosting" section.
   - Click on "Edit" and enable static website hosting.
   - Specify the index document (e.g., index.html) as the default homepage.
   - Save the changes.

3. **Ensure Public Reads:**
   - Confirm that public reads are allowed on the S3 bucket.
   - Adjust block public access settings if necessary.
   - Attach an S3 bucket policy to allow public access.

4. **Upload Index Document:**
   - Upload the specified index document (e.g., index.html) to the S3 bucket.

5. **Access Website URL:**
   - Copy the bucket website endpoint URL provided in the static website hosting settings.
   - Paste the URL in a web browser to access the static website.
![Index Outcome](<../../readme-images/S3/index outcome.png>)

## Example Result

After enabling website hosting and uploading an index.html file, accessing the bucket website endpoint should display the static website. For instance, if the website shows "I love coffee" and displays images, it indicates that the S3 bucket is successfully configured for hosting static content.

## Important Note

Ensure that public reads are allowed, and the S3 bucket policy allows public access. Without proper public access settings, users may encounter 403 forbidden errors when trying to access the website.


