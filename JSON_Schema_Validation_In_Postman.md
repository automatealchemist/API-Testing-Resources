
# **JSON Schema Validation**

**JSON** stands for **JavaScript Object Notation**, which is a lightweight format for storing and transporting data. It is often used when data is being sent from a server to a web page. JSON is self-describing and easy to understand.

It basically follows the **key-value pair** format.  
For example, when we hit an API endpoint, we get the response in a key-value pair format — and that response is called **JSON**.

---

## **What is JSON Schema?**

**JSON Schema** is a contract for our JSON document that defines the expected data types and the format of each field in the response.

It represents data in a machine-readable format for complete structural validation — useful for automated testing and validating client-submitted data.

---

## **Importance of JSON Schema Validation**

1. Using a JSON schema to construct a model of our API response makes it easier to validate that our API is returning the data it should.
2. It helps in monitoring API responses and ensures they adhere to a specified format.
3. It helps in getting alerted when **breaking changes** occur.

---

## **Example JSON Response**

```json
[
  {
    "first_name": "abc",
    "last_name": "xyz",
    "age": 24
  }
]
```

---

## **Basic JSON Schema Example**

```json
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "type": "array",
  "items": {
    "type": "object",
    "properties": {
      "first_name": { "type": "string" },
      "last_name": { "type": "string" },
      "age": { "type": "number" }
    }
  }
}
```

> If we receive a number instead of a string in "first_name", the JSON schema validation will fail.

---

## **How to Create and Use JSON Schema for API Validation**

1. Go to [jsonschema.net](https://jsonschema.net) and create a JSON schema.
2. Paste the actual API response on the website and generate the schema.
3. Copy the generated schema.
4. Paste it inside the **Tests** tab in Postman, but wrap it inside JavaScript code as shown below.

---

## **Postman Tests Tab Code Snippet**

```javascript
const schema = {
  // Paste your JSON schema here
};

const data = pm.response.json();

pm.test("Validates schema", function () {
    pm.expect(tv4.validate(data, schema)).to.be.true;
});
```

---

## **How It Works**

Once the JSON schema is set in the above format:

- Every time we hit the API, the response will be validated against the JSON schema.
- If there is any mismatch in structure or data type, the test will fail and be shown in **Test Results**.

---

## **More Resources**

To explore more on JSON Schema Draft v4 and how it can be used to validate simple values and complex objects using a rich validation vocabulary, this website can be referred:   [tv4 GitHub Repository](https://github.com/geraintluff/tv4)

I created JSON schemas from real responses using:   [https://jsonschema.net/app/schemas/545960](https://jsonschema.net/app/schemas/545960)

---

That is how we can validate our API response with the help of JSON Schema.
