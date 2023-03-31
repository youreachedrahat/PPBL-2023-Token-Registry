Assignment / SLT 103.1

## Step By Step
1. Create a fork of this repo.
    - Go to [Token Registry repo](https://gitlab.com/gimbalabs/ppbl-2023/ppbl-2023-token-registry)
    - Look for the **Fork** button (upper right corner). Click on there. That will open a new window called *"Fork Project"*.  
    - Once in the *Fork Project* window, go to the **Project URL** field. In the option *"Select a namespace"*, select **your** GitLab username.
    - Click on the **Fork Project** button.
    - Final result: your own copy (your fork) of the *Token Registry repo* with the URL *gitlab.com/**your-gitlab-username**/ppbl-2023-token-registry*
2. Clone the repository locally (optional).
    - In your fork, look for the **Clone** button (on the right side). Click on there. 
    - Copy the URL corresponding to the *Clone with HTTPS* option.   
    - Open a terminal in your computer.
    - Go to the Root directory.
    - Once there, paste the URL accompanied by the `git clone` command, as follows:
        ```bash
        git clone https://gitlab.com/your-gitlab-username/ppbl-2023-token-registry.git
        ```
    - At this point, you would have your own copy of the Gimbalabs repository on your machine. This means that you could do whatever you want with this copy without fear of damaging the original repository.



3. Make changes
    - create a copy of `template.json` where the file name is the HEX name of your PPBL2023 Token
    - add details to your new `.json` file. See [example](/mappings/5050424c3230323344656d6f4765726f6c616d6f.json)
    - save
    - `git add .`
    - `git commit -m "I created a new .json file"`
    - `git push`
4. Push changes
5. Submit merge request


## Hex Notes
### Show how to use:
- https://string-functions.com/hex-string.aspx
- https://string-functions.com/string-hex.aspx

### Show how to search for Policy ID and/or Contributor Reference Address
> https://preprod.cardanoscan.io/
- policyID `05cf1f9c1e4cdcb6702ed2c978d55beff5e178b206b4ec7935d5e056`
- contract address `addr_test1wr6ewsvtmdjv8znh7wxvw9qezgwvju5rdk9gmgefvrvrhug7zrfe0`
