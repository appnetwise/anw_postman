# Voltacabs - Demand Hotspots API

## Overview

Welcome to the Voltacabs Demand Hotspots API repository! This repository contains the Postman collection for accessing demand hotspots data within the Voltacabs platform. The API empowers users to retrieve information about areas with high demand for taxi services.

## Getting Started

To get started with using the Postman collection, follow these steps:

### Clone the Repository
Clone this repository to your local machine
   
### Install Postman
If you haven't already, download and install Postman on your machine. You can download it from the [official website](https://www.postman.com/downloads/).
   
### Import the Collection
Import the Postman collection into your Postman application. Follow these steps:
   - Open Postman.
   - Click on the "Import" button located in the top left corner.
   - Choose the option to "Import From File" and select the collection JSON file from your local machine.
   - Click "Import" to add the collection to your Postman workspace.
     
### Set Up Environment Variables (if applicable)
If the collection relies on environment variables, follow these steps to set them up:
   - Click on the gear icon in the top right corner to access the Manage Environments.
   - Click on "Add" to create a new environment.
   - Define the necessary variables (e.g., base URL, API key) and save the environment.

### Exploring Requests and Responses

Before running the collection using the Collection Runner, you may want to manually explore the requests and responses to ensure that the endpoints are working as expected. Follow these steps to send requests and view responses within Postman:

1. **Open Postman**: Launch the Postman application on your machine.

2. **Import Collection (if not already imported)**: If you haven't already imported the collection into Postman, follow the "Import the Collection" section in the Getting Started guide.

3. **Select Request**: From the left sidebar, navigate to the collection and select the request you want to explore. Click on the request to open it in the request builder.

4. **Configure Request**: If necessary, configure any parameters, headers, or body data for the request. Make sure to provide any required authentication credentials if the request requires them.

5. **Send Request**: Once the request is configured, click on the "Send" button to send the request to the API server.

6. **View Response**: After sending the request, you will see the response returned by the API server in the response pane below the request builder. Review the response to ensure that it contains the expected data and does not contain any errors.

7. **Repeat for Other Requests**: Repeat steps 3-6 for other requests in the collection that you want to explore.

By manually exploring requests and responses in this way, you can verify that the endpoints are working correctly before running the collection using the Collection Runner.

 

## Running the Collection

### Manually with Collection Runner

To manually run the collection with Collection Runner in Postman, follow these steps:

### Configure Collection Runner

1. In the top menu, navigate to "Collection Runner".
2. In the Collection Runner window, select the desired collection.
3. Specify the number of iterations you want to run.
4. Optionally, configure delays or randomize the order of requests.
5. Click on the "Run [X] Iterations" button to start the collection run.

### Monitor Collection Run

Postman will execute each request in the collection for the specified number of iterations. You can monitor the progress of the collection run and review the responses in the Collection Runner window.

## Exporting Collection and Environment from Postman

### Export Collection

- Open Postman.
- Select the collection you want to export from the left sidebar.
- Click on the ellipsis (...) next to the collection name.
- Choose "Export" from the dropdown menu.
- Select "Collection v2" as the export format.
- Save the collection JSON file to your desired location.

### Export Environment:

- Click on the gear icon in the top right corner to access the Manage Environments.
- Select the environment you want to export.
- Click on the ellipsis (...) next to the environment name.
- Choose "Export" from the dropdown menu.
- Save the environment JSON file to the same location as the collection.

## Running the Collection Using Newman (Command Line)

If you prefer to run the collection using Newman, follow these steps:

### Install Newman

1. Ensure you have Node.js installed on your machine. You can download it from [here](https://nodejs.org/).
2. Then, install Newman globally via npm:
   ```bash
   npm install -g newman
   
### Run Collection with Newman

To run the collection using Newman, follow these steps:

1. Open your terminal or command prompt.
2. Navigate to the directory where the collection and environment JSON files are located.
3. Execute the collection using Newman:
   ```bash
    newman run [collection_file].json -e [environment_file].json

Replace [collection_file].json with the filename of the exported collection and [environment_file].json with the filename of the exported environment.

## Running the Collection Using Newman with the Postman API

To run the Postman collection using Newman with the Postman API, follow these steps:

1. **Generate an API key**: If you haven't already, generate an API key from your Postman account.
   
2. **Fetch a list of your collections**:
   - Navigate to: [https://api.getpostman.com/collections?apikey=$apiKey](https://api.getpostman.com/collections?apikey=$apiKey)
   - Replace `$apiKey` with your actual API key.
   - This will provide you with a list of your collections.
     
3. **Get the collection link via its UID**:
   - Once you've obtained the list of collections, find the UID of the collection you want to run.
   - Construct the collection link using the UID: [https://api.getpostman.com/collections/$uid?apikey=$apiKey](https://api.getpostman.com/collections/$uid?apikey=$apiKey)
   - Replace `$uid` with the UID of your collection and `$apiKey` with your actual API key.
     
4. **Obtain the environment URI**:
   
   - Navigate to: [https://api.getpostman.com/environments?apikey=$apiKey](https://api.getpostman.com/environments?apikey=$apiKey)
   - Replace `$apiKey` with your actual API key.
   - This will provide you with a list of your environments.
     
5. **Run the collection**:
   
   - Using the collection and environment URIs acquired in steps 3 and 4, run the collection as follows:
     ```bash
     newman run "https://api.getpostman.com/collections/$uid?apikey=$apiKey" \
         --environment "https://api.getpostman.com/environments/$uid?apikey=$apiKey"
     ```
   - Replace `$uid` with the UID of your collection and `$apiKey` with your actual API key.

By following these steps, you can effectively run your Postman collection using Newman with the Postman API for automated testing or integration purposes.
