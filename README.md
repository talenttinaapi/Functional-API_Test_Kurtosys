# Functional-API_Test_Kurtosys

This repository contains a functional API test for the website [Kurtosys](https://www.kurtosys.com). The test checks for specific criteria in the API response, including the status code, response time, and server header.

## Test Details

The test performs the following checks:

1. **Status Code**: Ensures the response status code is `200`.
2. **Response Time**: Ensures the response time is less than 2 seconds.
3. **Server Header**: Ensures the server header has a value of `cloudflare`.

## Tools Used

- **Postman**: A popular tool for API testing.

## Test Script

The test script used in Postman is as follows:

```javascript
// Status code assertion
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

// Response time assertion
pm.test("Response time is less than 2 seconds", function () {
    pm.expect(pm.response.responseTime).to.be.below(2000);
});

// Server header assertion with lowercase conversion
pm.test("Server header is Cloudflare", function () {
    pm.expect(pm.response.headers.get('Server').toLowerCase()).to.eql('cloudflare');
});
