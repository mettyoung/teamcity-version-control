# TeamCity Version Control Tutorial
[![TeamCity](https://img.shields.io/badge/TeamCity-2018.1.2-green.svg)]()

## Background 
### Problem encountered in Agile
In agile, development teams are shipping new code once, twice or sometimes three times a week instead of every six months or so. Manual shipping of code cannot be accommodated anymore as it takes longer than it should. As the software enters its second release phase, it becomes even more difficult. The development team now has to maintain at least three environments, the QA, staging and production environments. Each environment monitors different branches in the repository. Moreover, each environment shall have their own provision as they run on different code and infrastructure (such as databases). Now, the team is expected to ship code to QA many times a day, to staging many times a day during release phases and to production as many as required for the hotfixes. To top it off, different environment may even require different build automation scripts. 

### Significance of this project
Having said all that, there are now many tasks lined up for the cheerful DevOps engineer and all play an indispensable role in the game plan. One of which is the version control of the TeamCity build configuration as the software continues to evolve and require of them. One scenario that would benefit would be in changing the monitored branch to another release branch as the software enters its new release phase.

## Description
This is a simple tutorial to 
1. Create versioned settings
2. Update versioned settings
3. Load versioned settings

## Tutorial
### Getting started
1. Install docker and docker compose.
2. Clone this repostory.
3. Go to the root directory of the repository and run `docker compose up -d`.
3. Visit `localhost:8111` and complete the wizard with all the defaults.

### Create versioned settings
1. Create Project from GitHub with all the defaults.
2. Go to created project and click edit project settings.
3. Click versioned settings from the side nav.
4. Turn on synchronization.
5. Choose VCS root.
6. Tick `Use settings from VCS`.
7. (Optional) Tick `Show settings changes in builds`.
8. (Optional) Choose `Kotlin` in settings format.
9. Click `Apply`.
10. Click `Commit current project settings`.
11. Git pull upstream and verify the generated git commit.

### Update versioned settings 
1. Perform build configuration modification via TeamCity Web UI.
2. Go to created project and click edit project settings.
3. Click versioned settings from the side nav.
4. Click `Commit current project settings`.
5. Open newly committed files and follow the patch script advice.
6. Commit again without the patch script.

### Load versioned settings
1. Create Project from GitHub with all the defaults.
2. TeamCity detects settings.kts from the repository. 
3. Tick `Import settings from .teamcity/settings.kts and enable synchronization with the VCS repository` and proceed.

## Contributing to TeamCity Version Control Tutorial
Found anything that this project can improve of? Just open an issue along with detailed explanation.