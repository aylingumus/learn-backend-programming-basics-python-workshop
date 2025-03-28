# Workshop: Introduction to Backend Development with Python

Welcome, everyone! This workshop will be a fun and interactive introduction to backend development using Python. We’re going to get our hands dirty with code and explore how APIs work behind the scenes. By the end, you’ll have a strong grasp of the fundamentals and a practical sense of how to build your own Python-based apps. Let's dive in!

---

## 1. What is Backend Programming?

Backend programming is all about the parts of an application you don't see directly. Think about how data is stored, how servers handle requests, and how information is processed before being shown on a website or in an app. We'll discuss:
- **Server-side logic** vs. **Client-side (frontend)**  
- **Databases, servers, and APIs** as the backbone of most web applications  

![image](https://github.com/user-attachments/assets/942d8703-d282-4c74-b574-8292fa39b74e)

---

## 2. What is Python? Why Are We Teaching Python?

Python is a versatile, beginner-friendly language. Here's why we've chosen it:
- Readable syntax: easy to learn and understand.
- Large community and ecosystem: plenty of libraries for web development, data science, and more.
- Great for rapid prototyping and scaling apps.

We'll showcase how Python's simplicity makes it ideal for this hands-on workshop.

---

## 3. What is Google Colab? How Do We Use It?


[Google Colab](https://colab.research.google.com)

Google Colab is a free cloud-based notebook environment that lets us write and run Python code in our browser. We'll walk through:
- How to create a new notebook.
- Running cells to execute code snippets.
- Saving your work to Google Drive.

**Other Tools:**  
- **Jupyter Notebook:** Similar to Colab, but you run it locally on your computer if you prefer that setup.

---

## 4. Show Basic Python Commands

We'll start with the timeless tradition: **Hello World!**

```python
print("Hello World!")
```

We'll show you how to run this in Google Colab (or Jupyter). You'll see right away how quick it is to get feedback and see your program in action.

---

## 5. Variables & Basic Data Types
We'll explore how to store and work with data in Python. Topics will include:

- **Data types**: string, int, float (often called double in other languages), list, tuple, etc.

- **Declaring variables**:

    ```python
    age = 25
    name = "Alice"
    temperature = 36.5
    ```

- **User input and simple calculations**:

    ```python
    user_name = input("What is your name? ")
    print("Nice to meet you, " + user_name)
    ```

- **String functions**:

    ```python
    my_string = "Hello"
    print(len(my_string))  # Length of the string
    print(my_string.upper())  # Convert to uppercase
    ```

We'll practice these to make sure everyone is comfortable with basic Python operations.

---

## 6. If Condition & For, While Loops
Let's make our code smart! We'll see how to let Python "decide" what to do:

- **If statements**:

    ```python
    name = input("Enter your name: ")
    
    if name == "Eowyn":
        print("I know your face, Eowyn.")
    else:
        print("Good to see you again, " + name)
    ```

- **For loops**:

    ```python
     famous_women_in_tech = ["Ada Lovelace", "Hedy Lamarr", "Katherine Johnson"]
    
     for woman in famous_women_in_tech:
        print("The great " + woman)
    ```

- **While loops**:

    ```python
    count = 0
    while count < 5:
        print(str(count) + " bottles of beer on the wall")
        count += 1
    ```

We'll talk about how these loops work and best practices for avoiding infinite loops.

---

## 7. What is a Library? How to Use Them?
A library (or package) is a collection of prewritten code that helps us do more complex tasks. We'll learn:

How to install and import a library:

```python
import requests
```

Why libraries are awesome: they save time and let you focus on the cool parts of your project.

We'll highlight the specific libraries we plan to use in this workshop (like `requests` for making HTTP requests).

---

## 8. What is an API? Why Do We Use It?
An **API (Application Programming Interface)** lets different software systems talk to each other. We'll cover:

- Real-life examples: using a weather API to get current temperatures or a finance API to get stock prices.

- How APIs fit into backend programming.

- Sending requests and receiving responses.

---

## 9. What is JSON?
JSON (JavaScript Object Notation) is a common format for data exchange. We'll explain:

- **Content type and structure**: keys and values in a "`{}`" based format.

Why JSON is so common in web APIs.

How to make JSON data more readable, aka "pretty print".

```python
import json

data = {
    "name": "Alice",
    "age": 25
}
print(json.dumps(data, indent=2))
```

---

## 10. HTTP Verbs: POST, GET, and more
We'll talk about HTTP methods and when to use each one:

- **GET** for retrieving data.

- **POST** for sending data (like creating a new record).

- **PUT** and **PATCH** for updating.

- **DELETE** for removing data.

### 10.1 HTTP vs HTTPS
Now let’s talk about the difference between HTTP and HTTPS:

- **HTTP** stands for HyperText Transfer Protocol. It’s the underlying protocol used by the World Wide Web to define how messages are formatted and transmitted.

- **HTTPS** is HTTP with **SSL/TLS encryption**, adding a layer of security.

    - Encrypts your data in transit.
    
    - Protects sensitive information (like passwords, credit card details).

    - Websites with `https://` in the URL are more secure than those with `http://`.

---

## 11. API Token? What Is That?
APIs often require authorization. We'll learn:

- Why we need tokens or API keys.

- How to keep your token safe (never share it publicly).

- Examples of how to use tokens in requests.

---

## 12. App Building & Using an API (Hands-On!)
Now we'll roll up our sleeves and build a simple app that interacts with a real API. We'll use the [Carbon Interface API](https://docs.carboninterface.com/#/) to measure carbon emissions from various activities. Specifically, we'll explore:

- Electricity usage.

- Flight data.

- Shipping data.

If time allows, we'll also take a peek at the Carbon Ledger API. This is where you get to code along:

1. Sign up for an API key (token).

2. Make a GET request to fetch data.

3. Make a POST request to create a new record.

4. Parse the JSON response to display it nicely.

By the end, you'll have a simple, functioning mini-app that talks to the Carbon Interface API!

```python
import requests

url = "https://www.carboninterface.com/api/v1/estimates"
headers = {
    "Authorization": "Bearer API_KEY",  # Replace with your actual API key
    "Content-Type": "application/json"
}
data = { "type": "flight",
        "passengers": 2,
        "legs": [
          {"departure_airport": "sfo", "destination_airport": "yyz"},
          {"departure_airport": "yyz", "destination_airport": "sfo"}
        ]}

response = requests.post(url, headers=headers, json=data)
print(response.json())


# Extract and print the carbon_kg value
data = response.json()  # Now it's a dictionary
carbon_kg = data['data']['attributes']['carbon_kg']
print("Carbon emissions (kg):", carbon_kg)
```

---

## 13. Wrap-Up & Next Steps
We've covered a lot in these three hours! Here's a quick summary:

- You learned the basics of Python and backend development.

- You explored loops, conditionals, and variable manipulations.

- You discovered how to integrate APIs into your Python code using libraries like requests.

- You got hands-on experience using a real API to build a simple app.

### Now What?

- Consider setting up Python locally on your machine for more flexibility.

- Explore different libraries (like `Flask` or `Django`) for backend web development.

- Keep experimenting with public APIs, there are many out there!

Feel free to ask questions or reach out for resources. Happy coding and exploring!

**Thank you for joining us! We're excited to see what you build next.**
