## What is the difference between push, pull, and fetch?

- `git push` pushes changes from your tracking branch to its remote branch.
- `git pull` gets changes from the remote repo and merges them into your tracking branch.
- `git fetch` gets changes from the remote repo but doesn't merge them into your tracking branch.

Git users often describe `git fetch` and `git pull` as equivalent, but they aren't. Both fetch remote changes, but `git pull` automatically merges those changes into your tracking branch.

## How to use push, pull, and fetch

Use push, pull, and fetch when you want to share code with a remote repository. You can think of it as "make the remote branch resemble my local branch".

This example shows you how to use push, pull, and fetch when working on a shared branch called `shared-branch`.

1. Use pull to get the latest updates from the repository.

   ```bash
   git pull
   ```

2. Check out the branch.

   ```bash
   git checkout shared-branch
   ```

3. Change some code.
4. Commit your changes to your tracking branch.

   ```bash
   git commit -a
   ```

5. Check for updates to the remote branch before you push your changes.

   If there are conflicts between your tracking branch and the remote branch, your push fails. So incorporate remote updates before you push.

   You have two options:

     - `git pull`

        Be aware that `git pull` automatically updates your tracking branch files.

        ```bash
        git pull
        ```

        If there is a conflict, output is similar to:

        ```bash
        CONFLICT (content): Merge conflict in README.md
        Automatic merge failed; fix conflicts and then commit the result.
        ```

        Fix the conflicts and then commit your changes.

     - `git fetch` plus `git merge`

        This is the safer option because `git fetch` doesn't automatically update your tracking branch files. You must run `git merge` to merge the remote changes into your tracking branch.

        1. Fetch the remote branch.

           ```bash
           git fetch
           ```

        2. Merge remote updates into your tracking branch.

           ```bash
           git merge origin/shared-branch
           ```

           If there is a conflict, output is similar to:

           ```bash
           CONFLICT (content): Merge conflict in README.md
           Automatic merge failed; fix conflicts and then commit the result.
           ```

    Both options produce the same the same result, so choose 

6. Push your changes to the remote repository.

   ```bash
   git push origin shared-branch
   ```

## Related content

- `git push` [command reference](https://git-scm.com/docs/git-push)
- `git pull` [command reference](https://git-scm.com/docs/git-pull)
- `git fetch` [command reference](https://git-scm.com/docs/git-fetch)