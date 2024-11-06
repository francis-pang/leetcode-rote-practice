# Postman
This documents record the progress of setting up new API meant to query LeetCode API to retrieve information for my practice progress.

I have documented my API in the Postman Collection [https://www.postman.com/francis-lone-wolf/leetcode/overview](https://www.postman.com/francis-lone-wolf/leetcode/overview).

## 1. Getting credential
I was having trouble to get the credential past. I found out the login URL.

### Cross-site request forgery (CSRF)
I found out that the Leetcode website uses Django. Based on [what I read](https://hackernoon.com/automatically-set-csrf-token-in-postman-django-tips-c9ec8eb9eb5b), there is default CSRF protection mechanism in place. So I need to set the CSRF token in my request header. 

I learn this by sending a GET request on `/login`, retrieving the CSRF token in the resposne header`set-cookie`. I placed this value inside the HTTP header `X-CSRFToken`. 

However, there is still CSRF protection mechanism, as seen in the response below:
```
...
<body>
    <div id="summary">
        <h1>Forbidden <span>(403)</span></h1>
        <p>CSRF verification failed. Request aborted.</p>


    </div>

    <div id="explanation">
        <p><small>More information is available with DEBUG=True.</small></p>
    </div>

</body>
...
```

I have yet to resolve this problem yet.

## 2. Getting submission information
I was able to retrieve the list of past submission information using the GraphQL method `submissionList`.

## 3. Retrieve question banks
There are 2 GrahpQL methods to retrieve the list of questions on LeetCode. The first one is to query the panel question list. That is the same behaviour as you click on the question list button on the single question solving web page. The other one is to list all the essential questions on LeetCode. That is the same behaviour as you click on the Problem button on top of the Leetcode's landing page.

I have also found a Github repository which contains all if not most Leetcode GraphQL query: [Leetcode webpage GraphQL queries](https://github.com/akarsh1995/leetcode-graphql-queries)