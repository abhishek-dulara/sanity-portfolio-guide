# Guide to Add Sanity to Your Website!

Hello Guys,
Do you want to add new projects to your website without touching the code every single time? 

Normally, changing a website means opening the code, typing new things, and uploading everything again. But we can use a magic tool called **Sanity**. It gives you a beautiful Dashboard to just upload photos and type text, and it magically updates your website!

How you can do it

---

## Step 01: Create Your Sanity Magic Box 

First, you need to set up Sanity. Open your computer's **Command Prompt** inside your project folder and type this

```bash
npm create sanity@latest
```

* Log in with your Google or GitHub account.
* Answer the simple questions (like your project name). 
* Choose **"Clean project with no sample data"** when it asks.

---

## Step 02: What You Want to Save 

What kind of information you want to keep (like a Title, Photo, and Description).

1. Go inside your new Sanity folder.
2. Find the folder named `schemaTypes`.
3. Create a new file called `project.js`.
4. Copy and paste this code into `project.js`:

```javascript
export default {
  name: 'project',
  title: 'My Projects',
  type: 'document',
  fields: [
    { 
      name: 'title', 
      type: 'string', 
      title: 'Project Name' 
    },
    { 
      name: 'description', 
      type: 'text', 
      title: 'Short Description' 
    },
    { 
      name: 'image', 
      type: 'image', 
      title: 'Project Photo' 
    }
  ]
}
```

*(Note: Remember to import and add this `project.js` to your `index.js` file inside the schema folder!)*

---

## Step 03: Open the Dashboard & Add Data! 

Now Ok. In your terminal, type this:

```bash
npm run dev
```

* Click the link it gives you (usually `http://localhost:3333`).
* You will see your Sanity Studio. On the left side, click **"My Projects"**. 
* Click the pencil icon to add a new project, type your details, upload a photo, and click the green **Publish** button.

---

## Step 04: Show It On Your Website 

Now your data is safe in Sanity.
In your website's terminal (like React or Next.js), install the Sanity client:

```bash
npm install @sanity/client
```

Then, you can use this simple "Query" to ask Sanity for your projects:

```javascript
const myQuery = `*[_type == "project"]{
  title,
  description,
  "imageUrl": image.asset->url
}`
```

Use this data in your code, and you will get a beautiful list of your projects displayed on your screen!

---
**© abhishek-dulara** |
**Happy Coding**

