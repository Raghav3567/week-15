
# 📦 Week 15: Postman - Collections & Assertions

## ✅ Objective

Create a **Postman collection** that includes a **GET request** to a public API and implement basic **tests (assertions)** to validate the response.

---

## 📌 Steps to Complete the Assignment

### 1. Create a Collection
- Open Postman.
- Click **Collections** > **+ New Collection**.
- Name it something like `Week15-GET-Test`.

### 2. Add a GET Request
- Inside the collection, add a new **GET** request with this URL:
  ```
  https://jsonplaceholder.typicode.com/posts/1
  ```
- Save the request into your collection.

### 3. Add Basic Tests
- Open the **Tests** tab of the request and insert the following test scripts:

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response time is less than 500ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(500);
});

pm.test("Content-Type is JSON", function () {
    pm.response.to.have.header("Content-Type", "application/json; charset=utf-8");
});

pm.test("Response body contains userId", function () {
    const jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property("userId");
});
```

---

## ▶️ How to Run the Collection

1. Open Postman.
2. Go to the **Collection Runner**.
3. Select the collection `Week15-GET-Test`.
4. Click **Run**.
5. Verify that all tests pass.

---

## 📁 Submission Requirements

- ✅ Exported Postman Collection (`.json`)  
  *(Postman → Click on your collection → 3 dots → Export)*

- ✅ Screenshot of Test Results  
  *(Example provided below for reference)*

---

## 📷 Example Screenshot

![Postman Test Screenshot](A_screenshot_of_Postman,_an_API_development_and_te.png)
