# CSV-to-HTML-Viewer-Transforming-Data-with-Cloud-Functions
Discover this GitHub repo featuring a Google Cloud Function that effortlessly converts CSV data from Google Cloud Storage into an HTML table and embeds the JSON representation of the data within the HTML. The Cloud Function is triggered by HTTP requests, serving up your data with ease.

## Usage

To use this Cloud Function, follow these steps:

1. **Create a Google Cloud Platform (GCP) Project:**
   - Sign in to the Google Cloud Console: https://console.cloud.google.com/.
   - Create a new project or select an existing one.

2. **Enable Required APIs:**
   - Navigate to the "APIs & Services" > "Library" section in the Cloud Console.
   - Enable the Cloud Functions API and Cloud Storage API for your project.

3. **Prepare the CSV Data:**
   - Ensure that the CSV file you want to convert (`googleplaystore.csv` in this example) is stored in a Cloud Storage bucket accessible to the Cloud Function.

4. **Deploy the Cloud Function:**
   - Select the Google Cloud project you want to work on.
   - Go to the "Cloud Functions" section in the Cloud Console.
   - Click on the "Create Function" button.
   - Fill in the details, such as “function name”, select “region”, and select trigger as “HTTP”.
- You can select “Allow unauthenticated invocations” if you want anyone to access your function. Be careful, as this will access the data stored in the storage bucket. Therefore, avoid storing sensitive information!
- Select the “runtime” you wish to write your function in. I have chosen Python for this demonstration. 
- Download the  “http-triggered-function.zip” and extract the source code of the function. Copy the contents of “main.py” and “requirements.txt” respectively. 
- Replace the “bucket_name” with the storage bucket name in your cloud project.
- Replace the “file_name” with the name of the .csv file stored in the bucket.
   - Click on the "Create" button to deploy the function.

5. **Trigger the Function:**
   - Once the function is deployed, it will be assigned a URL endpoint.
   - Send an HTTP request to the endpoint to trigger the function. (You can use “Postman” to achieve this). 
   - Alternatively, you can copy the URL and paste it into your web browser.
   - The function will retrieve the CSV data, convert it into an HTML table, and embed the JSON representation within the HTML.

## Functionality

- The function downloads a CSV file from Cloud Storage.
- It parses the CSV data and generates an HTML table.
- The JSON representation of the data is embedded within the HTML using a `<script>` tag.
- The HTML response is returned to the client.

