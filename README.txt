# Step 1: Authenticate with Google Cloud
gcloud auth login
gcloud config set project your-project-id

# Step 2: Create a Google Cloud Storage Bucket
gsutil mb -l us-central1 gs://ravi-my-private-bucket/

# Step 3: Upload Files to the Bucket
gsutil cp ./John_P-Doe_Demo_fee_estimate_2023-converted.pdf gs://ravi-my-private-bucket/

# Step 4: Verify File Upload
gsutil ls gs://ravi-my-private-bucket/

# Step 5: Make the File Public (Optional)
gsutil acl ch -u AllUsers:R gs://ravi-my-private-bucket/John_P-Doe_Demo_fee_estimate_2023-converted.pdf

# Step 6: Get the Public URL for the File (Optional)
https://storage.googleapis.com/ravi-my-private-bucket/John_P-Doe_Demo_fee_estimate_2023-converted.pdf

# Step 7: Download a File from the Bucket
gsutil cp gs://ravi-my-private-bucket/John_P-Doe_Demo_fee_estimate_2023-converted.pdf ./local-directory/

# Step 8: Check IAM Permissions of the Bucket
gsutil iam get gs://ravi-my-private-bucket/
