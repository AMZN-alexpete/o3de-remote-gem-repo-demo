# O3DE Remote Gem Repo Demo

This repository contains:
1. An asset gem named `RemoteGemDemo`
2. A `repo.json` file containing information about this remote o3de repository
3. A GitHub release with the .zip containing the gem and associated gem.json


## How this demo was made

1. Create a public GitHub repository for the gem
1. Create a gem named `RemoteGemDemo` using the `AssetGem` template and output it in the c:\remote-gem-demo folder 
    ```
    cd c:\o3de
    scripts\o3de.bat create-gem -gn RemoteGemDemo -tp Templates\AssetGem -gp c:\remote-gem-demo 
    ```
1. Create the local git repository, commit the initial contents and push
    ```
    cd c:\remote-gem-demo
    git init .
    git checkout -b main
    git add .
    git commit -sm "Initial commit"
    git remote add origin https://github.com/AMZN-alexpete/o3de-remote-gem-repo-demo.git
    git push -u main origin
    ``` 
1. Create a repo.json file and add the following information, but replace the owner and repository names in the URLs with your own GitHub owner and repository names.   
    ```
    {
        "repo_name":"RemoteGemDemo",
        "origin":"AMZN-alexpete",
        "repo_uri": "https://raw.githubusercontent.com/AMZN-alexpete/o3de-remote-gem-repo-demo",
        "summary": "A Gem Repository with a single Gem in the root of the repository.",
        "additional_info": "See the README.md at the root of this repository for more information",
        "last_updated": "2022-07-06",
        "gems": [
            "https://raw.githubusercontent.com/AMZN-alexpete/o3de-remote-gem-repo-demo"
        ]
    }
    ```

### Option #1 - Use GitHub Archive to generate the gem package
1. Edit your `gem.json` file and add/update the `repo_uri` and `origin_uri` fields
    ```
    "repo_uri": "https://raw.githubusercontent.com/AMZN-alexpete/o3de-remote-gem-repo-demo",
    "origin_uri": "https://github.com/AMZN-alexpete/o3de-remote-gem-repo-demo",
    ```
1. Save and close the file
1. Commit and push the updated `gem.json` file
    ```
    cd c:\remote-gem-demo
    git add gem.json
    git commit -sm "Updated gem URI"
    git push
    ```
### Option #2 - Create a GitHub Release and upload your own gem .zip as one of the release files
1. Zip up the contents of the gem folder (c:\remote-gem-demo)
1. Create a GitHub release and publish it
1. Upload your gem .zip as a file in the release and copy the download URL for the file
1. Edit your `gem.json` file and add/update the `repo_uri` and `origin_uri` fields
    ```
    "repo_uri": "https://raw.githubusercontent.com/AMZN-alexpete/o3de-remote-gem-repo-demo",
    "origin_uri": "https://github.com/AMZN-alexpete/o3de-remote-gem-repo-demo",
    ```
1. Save and close the file
1. Commit and push the updated `gem.json` file
    ```
    cd c:\remote-gem-demo
    git add gem.json
    git commit -sm "Updated gem URI"
    git push
    ```
