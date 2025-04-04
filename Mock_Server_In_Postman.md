## Mock Server

A Mock Server is basically a fake or dummy server that acts as an original server. It helps users conduct API testing when the real server is not available.

During API Testing, if the server is down or not yet ready, users can create a mock server and use it. This can be really helpful in the early development and testing stages. Once the real server becomes available, we just need to update the endpoint, and everything will switch from the mock server to the real server.

If the API server is not ready — whether for testers or developers — they can still test the API using a mock server.

Also, there might be situations where the API you need to test depends on another API that is not yet ready. In such cases, developers can create a mock server to simulate the dependent API.

---

## Steps to Start and Use a Mock Server:

1. Navigate to **Postman**.
2. Ensure the **Mock Servers** option is visible in the left-side navigation menu.
3. If not visible, click **"Configure workspace loader"** on the left side and enable **Mock Servers**.
4. Click on the **"Mock Servers"** option and then click on **"Create Mock Server"**.
5. Click on **"Create a new collection"**, and under **"Add Requests"**, the following 4 options will be available:
   - Request Method  
   - Request URL  
   - Response Code  
   - Response Body  
6. Add the endpoint path in the **Request URL**, choose the **Response Code**, and define the **Response Body**. Enter a mock server name and save the response.
7. Once the mock server is successfully created, navigate to **Collections** and click on the mock server collection.
8. Hit the API and observe the response.
9. In case the mock server needs to be private, you will need to add a **Postman API Key**:
   - Navigate to the **Authentication** tab of the APIs in the mock server collection.
   - Click on the **Authentication Method**, select **API Key**, add a name, and enter your Postman API Key.
10. Now again, hit the API and see the response.

---

## Example

Go to [reqres.in](https://reqres.in) and copy the APIs you want to test using the mock server.

Paste the API details one by one in the mock server setup, including:

- Request URL  
- Response Body  
- Response Code  

In this example, 2–3 APIs were taken: **GET**, **POST**, and **DELETE**.

Once they are added:

- Give a name to the mock server
- Navigate to the collection
- Select the desired API
- Execute it and verify the response

---

## Creating and Using a Mock Server for an Existing API Collection

1. Execute the APIs and **save the responses** of the APIs as examples.
2. Navigate to the **Mock Servers** section and create a new mock server by giving it a name. If you want to keep it private, make sure to select that option as well.
3. Once the mock server is created, **copy the mock server base URL** and paste it in the **base URL** field of the saved responses (examples) of the APIs.
4. Now execute those examples, and the same responses will be visible — just like hitting the real server, but using the mock one.

---


