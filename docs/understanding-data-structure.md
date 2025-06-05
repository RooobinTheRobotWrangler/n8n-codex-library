# Understanding the Data Structure in n8n

In n8n, **data is passed between nodes** in the form of **items**, each of which is a JavaScript object containing `json`, `binary`, and `pairedItem` properties.

---

## 🔸 What is an Item?

An **item** is the basic unit of data that moves through an n8n workflow. Think of it as a single row in a spreadsheet or a single record in a database.

An item looks like this:

```json
{
  "json": {
    "name": "John",
    "email": "john@example.com"
  }
}
{
  "json": {
    "filename": "photo.jpg"
  },
  "binary": {
    "data": {
      "data": "base64-encoded-string",
      "mimeType": "image/jpeg",
      "fileName": "photo.jpg"
    }
  }
}
Data Flow
Data flows top to bottom, node to node.

Each node receives an array of items.

Each item is processed independently unless merged.

Common Nodes for Data Manipulation
Node	Purpose
Set	Add, rename, or remove fields
Code	Run JavaScript per item
Merge	Combine data from two inputs
IF	Route based on conditions

Code Node Example
javascript
Copy
Edit
item.json.fullName = item.json.firstName + ' ' + item.json.lastName;
return item;
Best Practices
Keep data in json unless handling files.

Use “Execute Node” to view input/output at each step.

markdown
Copy
Edit

**4.** Scroll down. In the **commit message box**, type:

Add: docs/understanding-data-structure.md

yaml
Copy
Edit

**5.** Select: `Commit directly to the main branch`  
**6.** Click: **Commit changes**

---

Say **“next file”** and I’ll give you the next one the same way.
