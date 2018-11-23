# Chatterbox Skills Repo
![logo](https://avatars1.githubusercontent.com/u/14171097?v=4&s=200 "Logo")

# Content
- [Welcome](#welcome)
  - [How to Submit a Skill](#how-to-submit-a-skill)
    - [1) Make a Repo](#1-make-a-repo)
    - [2) Clone Repo](#2-clone-repo)
    - [3) Generate Readme](#3-generate-readme)
    - [4) Add Submodule](#4-add-submodule)
    - [5) Modify Skills Repo README.md](#5-modify-skills-repo-readmemd)
    - [6) Submit PR (Pull Request)](#6-submit-pr-pull-request)
    - [CSM Compliance](#csm-compliance)


# Welcome

The official home of skills for the Chatterbox ecosystem.  These skills are written by both the ChatterboxAI team and others within the Community.

## How to Submit a Skill

### 1) Make a Repo
Create the skill in a repo under your own Github user account.  You can 
follow the guide at [How To Make a Repo](https://help.github.com/articles/create-a-repo/), or use the [skiller.sh script](https://github.com/GigundoAI/chatterbox-core/blob/dev/skiller.sh).

### 2) Clone Repo
Clone the chatterbox-skills repo to a local directory, [How To Clone](https://help.github.com/articles/cloning-a-repository) if you are unfamiliar with the process.

```git clone https://github.com/GigundoAI/skills-repo.git```

### 3) Generate the README.md
All skills must have a standard README.md.  You can use the [Meta Editor](http://rawgit.com/GigundoAI/chatterbox-skills/master/meta_editor.html) to create it.

### 4) Add your Skill as a submodule
Add the your skill to this repo as a submodule.  You can type the following in the terminal of within your clone of
the chatterbox-skills repo.
```
git submodule add $remote $name-of-your-skill
```
Where ```$remote``` is the git address for your repo (for example "https://github.com/GigundoAI/skill-configuration") and
```$name-your-skill``` is the name used to install it via MSM or "Hey Chatterbox, install ...".  The recommended format for skill names is "publisher-descriptive-name", where 'publisher' is a unique name for you or your organization.  For example, "penrod-nautical-speed-translator".

When picking a name keep in mind that the installer will match by whole words between the dashes.  So if a user says
"install speed translator" it will look for all skills in the repo with the words 'speed' AND 'translator'.  That
means it will find "penrod-nautical-speed-translator" but would not find "abc-nautical-speeds-translator".  Make
sure the pieces of the name are 'speakable' to allow verbal installs.  That means "fubar-v2timer" would be a bad
name since you can't speak "v2timer" as a word.  A better name would be "fubar-timer-v2" or "fubar-timer-version-2".

The above command should have modified the .gitmodules file and added something similar to the bottom of the file:
```
+[submodule "NAME-OF-YOUR-SKILL"]
 +	path = YOUR-SKILL-REPO (or any unique path withing the chatterbox-skills repo)
 +	url = https://github.com/USERNAME/YOUR-SKILL-REPO.git
```

For more help, feel free to check out this [guide to working with submodules](https://github.com/blog/2104-working-with-submodules)

### 5) Modify this README.md
Modify the table section below to include the direct link to your repo.  Including the break HTML tag and an example phrase
or two that trigger your skill:

```
| :heavy_check_mark:  | [home-assistant](https://github.com/btotharye/chatterbox-homeassistant#readme)| Control your devices in home-assistant<br>```turn on office``` |

```
Chose an appropriate status icon from the list below:

**Status:**  
:heavy_check_mark: good working order  
:construction:     still being developed and not ready for general use (for reference/collaboration)  
:question:         untested (by us)  
:skull:            Broken, but good for ideas!

### 6) Submit a PR (Pull Request)
Once you've got your local version of the repo organized properly, submit a PR.

### MSM Compliance
To make your skill capable of being installed via MSM (the Chatterbox Skill Manager) you can include two additional files.

##### requirements.txt
A list of all Python modules which must be installed for it to work.  These will be installed via the Python PIP utility

##### requirements.sh
A script to run that will perform any additional steps needed to prepare the system for your skill.  This can include package installations.


**Status meaning:**  
:heavy_check_mark: good working order  
:construction:     still being developed and not ready for general use (for reference/collaboration)  
:question:         untested (by us)  
:skull:            Broken, but good for ideas!

For an example pull request , check out [this PR](https://github.com/GigundoAI/skills-repo/pull/1)
