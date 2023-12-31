Assignment / SLT 103.1

# Using Git

## Contrib Tokens

The Version Control System "Git" is the way developers interact with each other.  It is the tool they use to bring order to their workflow.  Specifically talking about the task of working with Git without dying several times in the attempt, the instructions we will provide in this section will allow you to get on the dance floor.  For sure you will still experience complications and there will be days of confusion. However, we can assure you of one thing: with every line of code you modify and then commit and merge request, with every project you fork and modify on your own machine, with every collaboration you support through the famous Git Version Control System, you will get stronger. It's a reward for your courage.

So, Let's start!

## GitLab
[GitLab](https://gitlab.com/) and [GitHub](https://github.com/) are similar. Both make Git more user-friendly.

GitLab and GitHub provide two essential services:
1. Repository hosting: GitLab and GitHub allow developers to upload, store, and share projects, including coordination of Git version control. GitLab and GitHub make it easier to use Git, much like a wallet makes it easier to interact with Cardano.
2. Developer social network: GitLab and GitHub allow developers to collaborate, share ideas, make plans, and build reputation through contribution.

### Prerequisite:
At Gimbalabs, we use GitLab. To fully participate in Plutus PBL 2023, you will neeed a GitLab account.

## Step By Step
### 1. Create a fork of this repo.
- Go to [Token Registry repo](https://gitlab.com/gimbalabs/ppbl-2023/ppbl-2023-token-registry)
- Look for the **Fork** button (upper right corner). Click on it. A new window called *Fork Project* will open.
- Once in the *Fork Project* window, go to the **Project URL** field. In the option *"Select a namespace"*, select **your** GitLab username.
- Scroll down the page and click on the **Fork Project** button. This action will take you directly to your fork (your own copy) of the *Token Registry repo* with the URL *gitlab.com/**your-gitlab-username**/ppbl-2023-token-registry*

### 2. Clone the repository locally (optional).
- In your new fork, look for the **Clone** button (on the right side). Click on it.
- Copy the URL corresponding to the *Clone with HTTPS* option.
- Open a terminal in your computer.
- Go to your `/ppbl2023` directory (or wherever you are saving other course repos).
- Once there, paste the URL accompanied by the `git clone` command, as follows:
```bash
git clone https://gitlab.com/your-gitlab-username/ppbl-2023-token-registry.git
```

At this point, you will have your own copy of the Gimbalabs repository (your fork) on your machine. This means that you can do whatever you want with this copy without fear of damaging the Gimbalabs original repository.

- Next, open the directory of your fork:
```bash
cd ppbl-2023-token-registry
```

- You have to add the original repository, in this case the Gimbalabs repository, as a *remote*:

```bash
git remote add upstream https://gitlab.com/gimbalabs/ppbl-2023/ppbl-2023-token-registry
```

This action establish a connection between the Gimbalabs repo and your fork. This connection is key to make possible many interaction between both repositories.

- Execute the command `git branch`. That command let you see how many *branches* you have currently in your project.  In this moment, you should have only one: the **main branch**.

- While you can do whatever you want with your copy of the repository, you might want to treat your copy with the same care you would treat the Gimbalabs repo. So let's create a new branch. That branch will be your **working-branch**:
```bash
git checkout -b working-branch
```
You can change *working-branch* to any name you choose. For example, `git checkout -b lesson-1031` would be a descriptive branch name.

That action will take you directly to the **working-branch**, so you will do your assignment in that branch.You can check it using the `git branch` command.

- Finally, execute the command `code .` to open your *development environment* and start to make changes.

> **Note: The Development Environment is a workspace for developers to make changes to the files that comprise a project.  If you don't have yet an IDE installed in your machine, the usual election is Visual Studio Code. So go to the [VS Code official site](https://code.visualstudio.com/) and install it like any other software.  Once you have VS Code open, go to the *extensions* tab (at the left of the screen) and search and install the *Remote Development* extension.**

### 3. Make changes.

> # Basic Routine:
> - create a copy of `template.json` where the file name is **the HEX name of your PPBL2023 Token**
> - add details to your new `.json` file. See [example](/mappings/5050424c3230323344656d6f4765726f6c616d6f.json)
> - save

You can accomplish your assigment without going through the step 2 (but believe me: for your career as Developer you need to practice and gain experience in step 2). So let's see the two options: directly from GitLab (without the step 2), and using your own development environment (applying the step 2).

Each option will cover the *Basic Routine* described above.

#### Hex Token Name:
- In a new tab, go to [Cardanoscan](https://preprod.cardanoscan.io/).  In the Cardanoscan Preprod explorer, paste this PolicyID:

`05cf1f9c1e4cdcb6702ed2c978d55beff5e178b206b4ec7935d5e056`

That action will show you a list. Search for your PPBL2023 Token on that list.  On the list, look for your token. You should notice that there are two tokens with your token name. One starts with `100`, and the other starts with `222`. Copy the token name after the first three digits (starting with `PPBL2023`).

- Next, in a new tab of your web browser, go to the [Hex To Text Converter Online Tool](https://string-functions.com/string-hex.aspx). In the field "*Enter the text to encode to hex*", paste your token's name. Then, click in the *Convert!* button.
- Copy the hexadecimal provided by the field "*The encoded string*" as a result. The string should start with `5050424c`, which is the hex equivalent of "PPBL".

#### Step 3 - Option #1 - Contribute Directly from GitLab.com:
- Now, go to your fork at GitLab (*gitlab.com/**your-gitlab-username**/ppbl-2023-token-registry*). Once there, look for and click in the **Web IDE** button (at the left side of the *Clone* button). That action will open a VS Code console in your web browser, ready to edit code.

Located at VS Code:
- create a new file inside the `/mappings` folder. The name of the file should follow the format: `Hex_obtained_previously.json`. For example: `5050424c323032337061626f6e5f736562.json`
- Next, open the file `template.json` and copy all its content (because it's a template).
- Go back to your `.json` recently created and paste there the `template.json` content.
- Take a look at the file `5050424c3230323344656d6f4765726f6c616d6f.json` inside in the `mappings` folder: that file is our guide, your *example* file. Following the data structure there fill your own file. All information is optional, so feel free to leave any of the `values` blank. For example, `DemoGerolamo` does not share any `contactData`.

>Note 1: the object `contactData` is a List ([]). In that List you can include the contact information you want to make public: your telegram, your twitter, your discord, etc. Each of these data must be enclosed in quotation marks and each one must be separated by commas. For example:
```bash
["telegram: sb_pabon", "discord: Sebastian Pabon#5894"]
```

>Note 2: If you give a closer look to the field `subject` in the *example* file, you'll notice that the name of the file and the content of that field are a little bit similar.

>Note 3: each String chunk (the content between quotes) has a limited capacity, 64 characters maximum. So if you want to include information that exceeds that limit, you will have to split the content into several Strings and separate them by commas. For example, in the field *bio*:

```bash
["I'm a Gimbalabs tutor and I love my students because they", "are the future of the ecosistem and", "the will create a better common reality for all of us."]
```
However, my recommendation is: make it simple. Write a brief and suscint message.

- Save your work.

Commit and Push your changes to your fork at GitLab:
- Go to the *Source Code* icon at the left side (after you save your work, a number inside a *bubble* emerge from that icon).
- In the "Commit message" field, write a message. For example: `I created a new .json file`.
- Click on the *Commit & Push* button. Inmediately a window pops up asking you: "*Commit to a new branch?*". Choose: "*No, Use the current branch "main"*"

Final result: you can go to your fork at GitLab, and see all the changes you made.  Congratulations! But remember: these changes are not part of the Gimbalabs repo yet. By make it possible, you have to submit a *Merge request*.


#### Step 3 - Option #2 - Edit Locally in VS Code:
This part is a continuation of  **Step 2. Clone the repository locally**. So first follow the instructions listed there.

In your local development environment:
- create a new file inside the `/mappings` folder. The name of the file should follow the format: `Hex_obtained_previously.json`. For example: `5050424c323032337061626f6e5f736562.json`
- Next, open the file `template.json` and copy all its content (because it's a template).
- Go back to your `.json` recently created and paste there the `template.json` content.
- Take a look at the file `5050424c3230323344656d6f4765726f6c616d6f.json` inside in the `mappings` folder: that file is our guide, your *example* file. Following the data structure there fill your own file. All information is optional, so feel free to leave any of the `values` blank. For example, `DemoGerolamo` does not share any `contactData`.

When you are ready:
- Commit and Push your changes from your **working-branch** to the **main branch** of your fork:
- Go to the *Source Code* icon at the left side (after you save your work, a number inside a "bubble" emerge from that icon).
- If you hover your mouse on the section *Changes*, a "+" sign will appear (among a few other symbols). Click on the "+" sign.

> You will notice that the changes will disappear from that section and reappear in the *Staged Changes* section.

- Time to *Commit* your changes: In the field "Message" (above the *Commit* button), write a message. For example: `I created a new .json file`. Next, click on the *Commit* button.
- Click on the *Sync Changes* button.

After that action, a small window will pop up asking for your *GitLab username*.

- Next, the same window will request a password. That password corresponds to your *Personal Access Token* that you can configure in the *Profile Settings* of your GitLab account, in the section "Access Tokens".

>Note: In the "Access Tokens" section you will generate your new *personal access token*.  That token will be a long string starting with the prefix *glpat*.  Once generated, you should copy it immediately and save it securely.

Partial result: if you go to your fork at GitLab and select your *working-branch*, you'll see all the modifications you made.  But, if you switch to your *main* branch, you will see that there are no modifications in that branch.

>So that, it's time to merge the modifications to the *main branch* of **your fork** (not yet to the Gimbalabs repo):

- Go back to your VS Code, go to the menu *Terminal* and open a *New Terminal*.

In the new terminal, execute:
```bash
git checkout main
```

Merge your *working-branch* into your *main branch*:
```bash
git merge working-branch
```
>Note: Don't forget: you have to replace *working-branch* for the name you assigned to your working branch.

Push the changes:
```bash
git push
```

Final result: if you go to your fork at GitLab and select your *main branch*, this time you'll see all the modifications you made.

### 4. Submit a Merge request.
In this step, you will request that your changes be included in the main repository, in this case the Gimbalabs repository.

- Located in your repo at GitLab, go to the **Merge requests** option (at the left side menu).
- Click on the *New merge request* button.
- Select the *Source branch*. Listen: **You are the source branch**.  In the "Select source branch" option, select *main*.
- Select the *Target branch*. Listen: **Gimbalabs is the target branch**.  In the "Select target branch" option, select *main*.
- Click on **Compare branches and continue**
- In the field "Title", write a concise but descriptive reference for your merge request.
- Scroll down the screen and click on **Create merge request** button.

#### And that's it. SLT complete. Congratulations my dear student: You are the best!

## Keep Exploring
- In the numeral **3. Make changes**, numeral **3.1 Directly from GitLab**, instruction *a*; when you are searching your token's name in [Cardanoscan](https://preprod.cardanoscan.io/), you can do it as well using the *Contributor Reference Address*: `addr_test1wr6ewsvtmdjv8znh7wxvw9qezgwvju5rdk9gmgefvrvrhug7zrfe0`
- In the numeral **3. Make changes**, numeral **3.1 Directly from GitLab**, instruction *b*; if you want to decode the Hexagesimal piece of data that you obtained thru the *Hex To Text Converter Online Tool*, go to [this page](https://string-functions.com/hex-string.aspx).
- These are really good GitLab guides:
    - https://docs.gitlab.com/ee/tutorials/make_your_first_git_commit.html
    - https://docs.gitlab.com/ee/gitlab-basics/start-using-git.html#clone-with-https
