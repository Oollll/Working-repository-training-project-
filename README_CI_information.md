# Information and requirements for the CI rollout.

## Information.

#### 1. In our project, the interaction between the repositories and CI is performed using webhooks that trigger CI every time a push to the repository data occurs:
```
adminka, mriyaranalytics, mriyarapi, mriyarapidb, mriyargarage, mriyarmp, mriyarmp-ui, mriyarns, mriyaros, mriyarpriceload, mriyarseo, mriyar_tasks, mriyar-compose
```

#### 2. CI connects to your server and runs ansible-playbook, which in turn works with the Makefile and runs all the relevant commands in a specific sequence.

#### 3. Pulling changes in repositories to the server is done using the repos-update function, which is described in the Makefile.
```
.PHONY: repos-update
repos-update:
	@for repo in $(REPOS); do \
		if [ -d ../$${repo} ]; then \
			echo "Updating $${repo} to branch $(BRANCH)..."; \
			( cd ../$${repo} && git checkout $(BRANCH) && git pull; ) \
		fi \
	done
```

## Requirements.

#### 1. Before starting the CI, you MUST upload the mriyar-compose repository to your server, otherwise the automation will not work.
```
git clone git@gitlab.mriyar.ua:root/mriyar-compose.git
```

#### 2. Change the value of the BRANCH variable in the Makefile if your main branch is different 
```
BRANCH = SPAR-52	
```

#### 3. Change the branch parameter in the .gitlab-ci.yml file to your main branch 

```
only:
    - SPAR-52

```