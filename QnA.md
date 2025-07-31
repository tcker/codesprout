### **Q1: What is the core problem we are trying to solve?**

**A:** The goal is to allow users to "upload" a photo and have it displayed on the website. The primary challenge is that our tech stack is limited to client-side technologies (HTML, CSS, JS) with no backend or database. This means we have no server to store the uploaded images.

### **Q2: What is the proposed solution?**

**A:** We will use the browser's built-in `localStorage`. This is a client-side storage mechanism that allows us to save data (in this case, the photos) directly in the user's browser.

### **Q3: How can we store an image file in `localStorage`?**

**A:** `localStorage` can only store data as strings. We will implement a JavaScript function that, upon a user selecting a file:
1.  Uses the `FileReader` API to read the image file.
2.  Encodes the image data into a **Base64 string**. This is a text representation of the image.
3.  Saves this Base64 string into `localStorage` as a key-value pair.

When the page loads, our script will check `localStorage` for any saved image strings and dynamically create `<img>` elements to display them. The `src` of these images will be the Base64 string itself.

### **Q4: What are the critical limitations of this approach?**

**A:** This is the most important part to understand. This solution has several key limitations:

1.  **Photos are NOT shared:** The photos are stored *only* in the browser of the user who uploaded them. A user in Chrome will not see photos uploaded by a user in Firefox, or by another person on a different computer. It is a **personal, local-only** photo dump, not a public, shared one.
2.  **Limited Storage:** `localStorage` is typically limited to 5-10MB per domain. This means a user can only store a few high-resolution photos before the storage is full.
3.  **Data is Not Permanent:** While `localStorage` persists between sessions, a user can easily wipe it by clearing their browser cache or data. It is not a reliable, long-term storage solution like a database.
4.  **No Server-Side Moderation:** Since the images never touch our server, we cannot enforce any content regulations or moderation. The "strict regulations" mentioned in the project idea cannot be implemented with this architecture.

### **Q5: Why are we choosing this solution despite the limitations?**

**A:** Because it is the *only* viable solution that adheres to the strict "vanilla HTML/CSS/JS, no backend" constraint. It allows us to build a working prototype of the core user-facing feature (selecting a file and seeing it on the page) without requiring any server infrastructure.

### **Q6: What is the future plan if we need a true, shared photo dump?**

**A:** If the project requires a shared gallery where all users can see all photos, we will need to introduce a backend. The current implementation will serve as a solid front-end foundation. The next step would be to replace the `localStorage` logic with API calls to a server that would handle image uploads, storage (e.g., using a service like AWS S3 or Firebase Storage), and retrieval.
