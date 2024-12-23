# Namaste React Course

## Chapter 01 - Inception

### Q: What is `Emmet`?  
A: `Emmet` is a powerful toolkit for web developers and designers that enhances HTML and CSS workflows. It helps in writing code quickly by providing shortcuts for common patterns.

#### Features of Emmet:
1. **HTML Expansion**:  
   Generate HTML using abbreviations.  
   Example: `div>ul>li.item$*3`  
   Output:
   ```html
   <div>
       <ul>
           <li class="item1"></li>
           <li class="item2"></li>
           <li class="item3"></li>
       </ul>
   </div>
   ```

2. **CSS Abbreviations**:  
   Example: `m10`  
   Output:
   ```css
   margin: 10px;
   ```

3. **Nested Elements**:  
   Use `>` to nest elements.  
   Example: `ul>li*3`  
   Output:
   ```html
   <ul>
       <li></li>
       <li></li>
       <li></li>
   </ul>
   ```

4. **Siblings**:  
   Use `+` to create sibling elements.  
   Example: `div+p+bq`  
   Output:
   ```html
   <div></div>
   <p></p>
   <blockquote></blockquote>
   ```

5. **Multiplication**:  
   Use `*` to create multiple elements.  
   Example: `ul>li*5`  
   Output:
   ```html
   <ul>
       <li></li>
       <li></li>
       <li></li>
       <li></li>
       <li></li>
   </ul>
   ```

6. **Numbering**:  
   Use `$` for incremental numbering.  
   Example: `ul>li.item$*3`  
   Output:
   ```html
   <ul>
       <li class="item1"></li>
       <li class="item2"></li>
       <li class="item3"></li>
   </ul>
   ```

7. **Grouping**:  
   Use parentheses `()` to group elements.  
   Example: `ul>(li.item$*2>a{Item $})*3`  
   Output:
   ```html
   <ul>
       <li class="item1">
           <a href="#">Item 1</a>
       </li>
       <li class="item2">
           <a href="#">Item 2</a>
       </li>
       <li class="item3">
           <a href="#">Item 3</a>
       </li>
   </ul>
   ```

---

### Q: Difference between a `Library` and `Framework`?  
| Aspect                   | Library                                 | Framework                                 |
|--------------------------|-----------------------------------------|-------------------------------------------|
| **Definition**           | A reusable collection of code for tasks | A structured foundation for an application|
| **Control**              | Developer controls the flow             | Framework controls the flow               |
| **Inversion of Control** | No inversion                            | Control is inverted                       |
| **Example**              | React.js                                | Angular                                   |

---

### Q: What is `CDN`? Why do we use it?  
A: `CDN` (Content Delivery Network) is a network of servers that delivers web content faster by serving it from the nearest server to the user.

#### Benefits of a CDN:
- **Improved Performance**: Faster loading times.
- **Scalability**: Handles high traffic efficiently.

---

### Q: Why is `React` known as `React`?  
A: React is called "React" because it efficiently **reacts** to changes in state and updates the UI dynamically.

---

### Q: What is `crossorigin` in a script tag?  
A: The `crossorigin` attribute is used when loading resources from different domains. It helps in handling security and privacy policies like the same-origin policy.

---

### Q: What is the difference between `React` and `ReactDOM`?  
| Feature           | React                                   | ReactDOM                                 |
|-------------------|-----------------------------------------|------------------------------------------|
| **Purpose**       | Core library for building UI components | Integration of React with the DOM        |
| **Example Usage** | Define components, state, and lifecycle | Renders React components to the DOM      |

---

### Q: Difference between `react.development.js` and `react.production.js` files via CDN?  
| File                     | Description                                                     |
|--------------------------|-----------------------------------------------------------------|
| **react.development.js** | Full version for development with warnings and debugging tools. |
| **react.production.js**  | Minified version for production without debugging code.         |

---

### Q: What is `async` and `defer` in the `<script>` tag?  
| Attribute          | Download Time          | Execution Time             | Order of Execution |
|--------------------|------------------------|----------------------------|--------------------|
| **async**          | Parallel with parsing  | Immediately after download | Unpredictable      |
| **defer**          | Parallel with parsing  | After HTML parsing         | Preserved          |

#### Usage Examples:  
**Async**:  
```html
<script src="script.js" async></script>
```

**Defer**:  
```html
<script src="script.js" defer></script>
```

