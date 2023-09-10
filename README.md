Yes, you can create a custom Git alias or shell script to automate these steps into a single command. Here's an example of how you can do it using a Git alias:

1. Open your Git configuration file. You can do this by running the following command:
    
    ```
    git config --global --edit
    
    ```
    
    This will open the global Git configuration file in your default text editor.
    
2. Add the following lines to create a custom alias named "gac" (short for "git add, commit, and push"):
    
    ```
    [alias]
        gac = "!f() { \\
            git add . && \\
            git commit -m \\"$1\\" && \\
            git push origin master; \\
        }; f"
    
    ```
    
    This alias defines a shell function that runs `git add .`, `git commit -m`, and `git push origin master` in sequence.
    
3. Save and exit the text editor.

Now you can use the "gac" alias to add, commit, and push with a single command:

```bash
git gac "Your commit message here"

```

Replace `"Your commit message here"` with your actual commit message.

This alias allows you to specify the commit message as an argument, making it faster to commit and push your changes.
