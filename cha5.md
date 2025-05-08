Here are detailed, exam-style answers for the **Chapter 5: Advanced Data Visualization** questions from the **Data Visualization** subject (3160717):

---

## 📘 Chapter 5: Advanced Data Visualization

---

### Q1. **What is Data Binding?**

**Answer:**

Data Binding is a process of connecting data to visual elements in data visualization frameworks such as D3.js. It allows the elements in a chart or graph to dynamically reflect the underlying data.

**In D3.js**, the `.data()` method is used to bind data to elements. This enables updating, adding, or removing elements based on data changes.

**Example in D3.js:**

```javascript
d3.select("ul")
  .selectAll("li")
  .data([10, 20, 30])
  .enter()
  .append("li")
  .text(function(d) { return d; });
```

Here, list items (`<li>`) are created based on the values in the array.

---

### Q2. **What are Data Joins? Explain with Example.**

**Answer:**

Data joins in D3.js are used to link data to DOM elements. It determines what elements should be **updated**, **entered**, or **removed** when the data changes.

**Three phases of data join:**

* **Enter** – new data values that do not have matching DOM elements.
* **Update** – existing elements with updated data.
* **Exit** – DOM elements that no longer have associated data.

**Example:**

```javascript
var data = [1, 2, 3];

var selection = d3.select("ul").selectAll("li").data(data);

selection.enter()
  .append("li")
  .text(d => d);

selection.exit().remove();
```

---

### Q3. **What is an Interactive Button? Explain with Example.**

**Answer:**

An interactive button is a UI element that triggers a function or visual change when clicked. In data visualization, it is used to **filter data**, **change views**, or **animate elements**.

**Example in HTML + D3.js:**

```html
<button id="btn">Update Chart</button>
<script>
  d3.select("#btn").on("click", function() {
    // Update chart logic
    alert("Chart Updated!");
  });
</script>
```

---

### Q4. **What is a Transaction? How is it applied in D3.js?**

**Answer:**

In D3.js, a transaction refers to the smooth transition of one state of a visual element to another. It is commonly used for **animations** such as color changes, resizing, or repositioning.

**Syntax:**

```javascript
d3.select("rect")
  .transition()
  .duration(1000)
  .attr("width", 200);
```

Here, the rectangle's width transitions to 200 over 1 second.

---

### Q5. **How to Add a Play Button to the Page? Explain with Example.**

**Answer:**

A Play button initiates a timed sequence (e.g., animation or data update) when clicked.

**Example:**

```html
<button id="play">Play</button>
<script>
  d3.select("#play").on("click", function() {
    d3.select("circle")
      .transition()
      .duration(2000)
      .attr("cx", 300);
  });
</script>
```

This moves a circle horizontally when the button is clicked.

---

### Q6. **How to Interrupt the Play Button?**

**Answer:**

To interrupt a play button animation, you use `.interrupt()` on the transitioning element.

**Example:**

```html
<button id="stop">Stop</button>
<script>
  d3.select("#stop").on("click", function() {
    d3.select("circle").interrupt();
  });
</script>
```

This stops the ongoing transition immediately.

---

### Q7. **How to Update Charts?**

**Answer:**

Updating charts involves changing the bound data and re-rendering the visual elements accordingly.

**Steps:**

1. Bind new data.
2. Update attributes like `x`, `y`, `height`, `width`.
3. Use transitions for smooth updates.

**Example:**

```javascript
svg.selectAll("rect")
  .data(newData)
  .transition()
  .duration(1000)
  .attr("height", d => d);
```

---

### Q8. **What is Sequence in Data Visualization?**

**Answer:**

Sequence refers to the **order in which animations or transitions are executed**. Proper sequencing improves the user’s understanding of how data changes over time.

**Example:**

```javascript
d3.select("rect")
  .transition().duration(500).attr("x", 100)
  .transition().duration(500).attr("fill", "blue");
```

Here, the rectangle first moves, then changes color.

---

Would you like me to format this as a printable PDF for your exam revision?
