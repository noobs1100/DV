Here are detailed, exam-style answers for **Chapter 4: Introduction to D3.js** from the **Data Visualization** subject (3160717).

---

# 📘 Chapter 4: Introduction to D3.js – DV Exam Answers

---

### Q1. **What is D3.js?**

**Answer:**

**D3.js** (Data-Driven Documents) is a powerful JavaScript library for creating interactive and dynamic data visualizations in web browsers using HTML, SVG, and CSS.

**Key Features:**

* Binds data to DOM elements
* Supports transitions and animations
* Allows manipulation of document elements
* Works well with large datasets and real-time data

**Example Use Case:** Creating bar charts, pie charts, or updating dashboards dynamically.

---

### Q2. **How to Make Selections in D3.js?**

**Answer:**

Selections in D3.js allow you to select and manipulate DOM elements.

**Basic Syntax:**

```javascript
d3.select("p")         // Selects the first <p> element
d3.selectAll("p")      // Selects all <p> elements
```

Once selected, you can modify their attributes or styles.

**Example:**

```javascript
d3.select("p").style("color", "blue");
```

---

### Q3. **What is the use of `select()` and `append()` in D3.js?**

**Answer:**

* `select()` – Selects the first matching DOM element.
* `append()` – Adds a new element as a child to the selected element.

**Example:**

```javascript
d3.select("body")
  .append("svg")
  .attr("width", 100)
  .attr("height", 100);
```

This adds an SVG element to the body.

---

### Q4. **What is the use of `selectAll()` and `exit()` in D3.js?**

**Answer:**

* `selectAll()` – Selects multiple elements.
* `exit()` – Handles data points that no longer have matching DOM elements (for removal).

**Example:**

```javascript
var data = [10, 20];
var sel = d3.select("ul").selectAll("li").data(data);

sel.enter().append("li").text(d => d);
sel.exit().remove();  // removes extra <li> not needed
```

---

### Q5. **Explain Data Joins in D3.js with Example.**

**Answer:**

A **data join** connects data to DOM elements using `.data()`. It helps manage what needs to be added, updated, or removed.

**Example:**

```javascript
var dataset = [5, 10, 15];

d3.select("ul")
  .selectAll("li")
  .data(dataset)
  .enter()
  .append("li")
  .text(d => d);
```

This creates list items (`<li>`) for each data point.

---

### Q6. **How to Load and Filter External Data in D3.js?**

**Answer:**

You can load external data formats like JSON or CSV using D3 functions like `d3.json()` or `d3.csv()`.

**Example:**

```javascript
d3.csv("data.csv").then(function(data) {
  var filtered = data.filter(d => d.age > 25);
  console.log(filtered);
});
```

**Steps:**

1. Load data
2. Filter using JavaScript array methods
3. Bind and display data

---

### Q7. **How to Deal with Asynchronous Requests in D3.js?**

**Answer:**

D3 handles asynchronous requests using **promises**. Methods like `d3.json()` or `d3.csv()` return a promise which resolves when the data is loaded.

**Example:**

```javascript
d3.json("data.json").then(function(data) {
  console.log("Data loaded:", data);
}).catch(function(error) {
  console.log("Error loading data", error);
});
```

This avoids blocking the UI and ensures data is processed once it’s available.

