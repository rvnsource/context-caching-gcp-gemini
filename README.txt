# Step 1: Authenticate with Google Cloud
gcloud auth login
gcloud config set project genai-434714

# Step 2: Create a Google Cloud Storage Bucket (Private Bucket Example)
gsutil mb -l us-central1 gs://ravi-my-private-bucket/

# Step 3: Upload Files to the Private Bucket
gsutil cp ./John_P-Doe_Demo_fee_estimate_2023-converted.pdf gs://ravi-my-private-bucket/

# Step 4: Verify File Upload to Private Bucket
gsutil ls gs://ravi-my-private-bucket/

# Step 5: Create a Public Bucket (Optional, if you want public access)
gsutil mb -l us-central1 gs://ravi-my-public-bucket/

# Step 6: Upload Files to the Public Bucket (Optional)
gsutil cp ./John_P-Doe_Demo_fee_estimate_2023-converted.pdf gs://ravi-my-public-bucket/

# Step 7: Make the Specific File Public (Only for Public Bucket)
gsutil acl ch -u AllUsers:R gs://ravi-my-public-bucket/John_P-Doe_Demo_fee_estimate_2023-converted.pdf

# Step 8: Get the Public URL for the File
https://storage.googleapis.com/ravi-my-public-bucket/John_P-Doe_Demo_fee_estimate_2023-converted.pdf

# Step 9: Download a File from the Private Bucket
gsutil cp gs://ravi-my-private-bucket/John_P-Doe_Demo_fee_estimate_2023-converted.pdf ./local-directory/

# Step 10: Make the Entire Public Bucket Public (Optional)
gsutil iam ch allUsers:objectViewer gs://ravi-my-public-bucket/

# Step 11: Check IAM Permissions of the Private Bucket
gsutil iam get gs://ravi-my-private-bucket/
