# Push to GitHub

**Local Git Repository**

1. Make the project directory a Git repository by running:

```bash
git init
```

2. Make sure that you have the `.gitignore` file and exclude the `node_modules` directory from version control:

```
node_modules/
``` 

3. Stage all the changes:

```bash
git add .
```

4. Commit the changes:

```bash
git commit -m  "Add message here"

```

**Part 3: Push to GitHub**

1. Create a new repository on GitHub:

- Go to the GitHub website .
- Click on the plus sign icon in the top right corner of the page, and then select "New repository."
- Fill in the details for your new repository:
   - Repository name: Choose a name for your new repository.
   - Description (optional): Add a short description to explain the repository's purpose.
   - Visibility: Choose between "Public" or "Private," depending on who should have access.
   - Do not initialize the repository with a `README` file or a `.gitignore` file.
- Click the "Create repository" button to create your new repository.


2. Link your local repository to the GitHub repository:

```bash
git remote add origin <GitHub Repository URL>
```

3. Push your local repository to GitHub:

```bash
git push -u origin main
```

4. Refresh the GitHub repository page to see your changes.

