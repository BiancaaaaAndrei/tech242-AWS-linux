# S3 Encryption Overview


![S3 Encryption Diagram](<../../readme-images/S3/s3 encryption.jpeg>)

## Server-Side Encryption

- **Default Encryption:**
  - Server-side encryption is the default mechanism whenever a new bucket is created or an object is uploaded to Amazon S3. This ensures that all objects are encrypted for security purposes.
  
- **Encryption Process:**
  - When a user uploads an object into Amazon S3, the object is automatically encrypted by Amazon S3 upon arrival in the bucket.
  
- **Server-Side Encryption Defined:**
  - The encryption process is performed by the server, hence the term 'server-side encryption.'

#### Client-Side Encryption

- **User-Initiated Encryption:**
  - In client-side encryption, the user takes the file, encrypts it before uploading, and then places it in the bucket. The encryption is initiated and controlled by the user.

- **Alternative Encryption Model:**
  - Unlike server-side encryption, which is the default, client-side encryption is user-dependent and involves the user actively encrypting the file before uploading.

#### AWS Encryption Models

- **Coexistence:**
  - Both server-side encryption and client-side encryption models coexist within AWS. However, it's essential to note that server-side encryption is always enabled by default.

