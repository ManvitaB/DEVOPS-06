# Milestone 3 (Pipeline > Deployment)

### Project Team:

- Manvita Balachandra ( mbalach )
- Prithvish Rakesh Doshi ( pdoshi )
- Vijaya Durga Kona ( vkona )

### System Dependency for Milestone 3:
- Linux OS
- Windows OS
- MAC OS with Intel processor

### Project Specification for Milestone 3:

[View Project Specification](https://github.com/CSC-DevOps/Course/blob/master/Project/M3.md) 

### Screencast for Milestone 3:
[View Screencast](https://www.youtube.com/watch?v=evVUiWuww24)

### Steps to setup repository of Milestone 3:
- `git clone https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06.git`

- `cd DEVOPS-06`

- `npm install`

- `npm link`

<b>NOTE:</b> Please place the rsa file in DEVOPS-06 directory upon cloning

#### Operating System Dependency:
Please run the following command from DEVOPS-06 directory
- `dos2unix pipeline/run-ansible.sh`
- `dos2unix pipeline/server-init.sh`

This can also be alternative set permanently for each user/system/project:<br>
Per system solution:<br>
`git config --system core.autocrlf false` 
<br>Per user solution:           
`git config --global core.autocrlf false`
<br>Per Project solution:            
`git config --local core.autocrlf false`  

Verify if the changes have appplied by running the below in the working directory :<br>
`git config core.autocrlf`

### Pipeline Commands to run Milestone 3:
`npm install`

`node index.js init`

Provision and configure computing environment for pipeline:

`pipeline init`
  
Trigger a build job, running steps outlined by build.yml, wait for output, and print build log:

`pipeline build itrust-build build.yml`<br>
`pipeline build mutation-coverage build.yml`

Provision and bring up the cloud VMs:<br>
`pipeline prod up`

Deploy itrust-deploy job to run with inventory file:<br>
`pipeline deploy inventory itrust-deploy build.yml`


### Template for .env file:
<b>Create .env file in the DEVOPS-06 directory:</b>`touch .env`

`GIT_TOKEN=<YOUR_GIT_ACCESS_TOKEN>`<br>
`GIT_REPO=github.ncsu.edu/engr-csc326-staff/iTrust2-v10.git`<br>
`MY_SQL_PASSWORD=devops-06`<br>
`VM_IP=192.168.56.10`<br>
`VM_USER=vagrant`<br>
`RSA_FINGERPRINT=<YOUR_RSA_FINGERPRINT>`

Once `prod up` is run, blue and green VM names and IP's write to the .env file

<b>NOTE:</b> Please use your personal GIT Access Token in place of `<YOUR_GIT_ACCESS_TOKEN>`

Set your digitalocean token on local system as below:
`setx DO_TOKEN <TOKEN>`

<b>NOTE:</b>
<br>
  Please use your personal digitalocean token in place of `<TOKEN>`<br>
  Please use your `<YOUR_RSA_FINGERPRINT>` to spawn your droplets from digitalocean

### Main Tasks Completed in Milestone 3:
- Ensure droplets are enabled on digitalocean with `pipeline prod up`
- Use SSH key for authentication for droplet creation
- Provision Digitalocean droplets via node js
- Script for `pipeline deploy` command
- Modification of iTrust2-v10 repository to ensure creation of war files
- Test iTrust deploy part using war files created by droplet
- Creating job specification for iTrust deployment using Tomcat
- Implementing blue green deployment stratergy on cloud servers
- Testing deployment script on blue/green servers

### Team Contirbution for Milestone 3:
- Ensure droplets are enabled on digitalocean with `pipeline prod up`: Prithvish Doshi
- Use SSH key for authentication for droplet creation: Prithvish and Vijaya Durga Kona
- Provision Digitalocean droplets via node js: Manvita Balachandra and Vijaya Durga Kona
- Script for `pipeline deploy` command: Vijaya Durga Kona
- Modification of iTrust2-v10 repository to ensure creation of war files: Manvita Balachandra and Prithvish Doshi
- Test iTrust deploy part using war files created by droplet: Manvita Balachandra
- Creating job specification for iTrust deployment using Tomcat: Manvita Balachandra and Prithvish Doshi and Vijaya Durga Kona
- Implementing blue green deployment stratergy on cloud servers: Prithvish Doshi and Vijaya Durga Kona and Manvita Balachandra
- Testing deployment script on blue/green servers: Vijaya Durga Kona and Manvita Balachandra and Prithvish Doshi

### Learnings/Experiences in Milestone 3:
- Time and Stress Management because of multiple submissions at the same time
- Blue Green Deployment stratergy
- Changes to be made for war file to execute
- Troubleshooting database password issues for iTrust2 login
- Running proxy for Blue/Green to deliver service with redirecting to a speceific server's application when one fails to render
- Using inventory file to run with generated details for blue/green deployment

### Issues Faced in Milestone 3:
- War file failing to execute on iTrust2-v10
- Modification of the iTrust codes to ensure war file is generated and able to render service
- Generalizing the IPs and access them dynamically
- Understanding and working of blue/green and proxy

### Screenshots of Execution for Checkpoint 3:

##### Pipeline init
<p align = "center">
<img width="900" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/Windows_M2_init.png">
</p>

#### iTrust Job 
<p align = "center">
<img width="900" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/ItrustM2.PNG">
</p>


##### Mutation coverage job
<p align = "center">
<img width="900" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/Windows_M2_mutation-coverage-build.png">
</p>

#### iTrust Deploy Job
<p align = "center">
<img width="900" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/M3deploy.PNG">
</p>

##### iTrust Deployment on Blue
<p align = "center">
<img width="900" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/Blue.jpeg">
</p>

#### iTrust Deployment on Green 
<p align = "center">
<img width="900" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/Green.jpeg">
</p>

#### iTrust Deployment on Proxy: 
<p align = "center">
<img width="900" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/proxy.jpeg">
</p>

### Project Board:

<p align = "center">
<img width=1200" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/1M3_ProjectBoard.PNG">
</p>

[View Project Board](https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/projects/3)

### Issue Board:

<p align = "center">
<img width="1000" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/2M3_issues.PNG">
</p>

[View Issue Board](https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/issues)

# Milestone 2 (Pipeline > Test+Analysis)

### Project Team:

- Manvita Balachandra ( mbalach )
- Prithvish Rakesh Doshi ( pdoshi )
- Vijaya Durga Kona ( vkona )

### System Dependency for Milestone 2:
- Linux OS
- Windows OS
- MAC OS with Intel processor

### Project Specification for Milestone 2:

[View Project Specification](https://github.com/CSC-DevOps/Course/blob/master/Project/M2.md) 

### Screencast for Milestone 2:
[View Screencast](https://youtu.be/v2nmkXZ_84M)

#### Mutation Coverage Formula:
There is a minor change in only displaying the formula in screencast (the calculation happening at the backend is correct):
- FAILED MUTATIONS does not include COMPILATION ERROR count, and hence the mutation coverage is FAILED / (TOTAL - COMPILATION ERRORS) which is 30% as shown.

### Steps to setup repository of Milestone 2:
- `git clone https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06.git`

- `cd DEVOPS-06`

- `npm install`

- `npm link`

- `npm install esprima`

- `npm install escodegen`

### Pre-requisites needed to run Milestone 2:
`js-yaml` is a dependency that is installed automatically. In case `pipeline init` gives an error related to `js-yaml`, please run the following command:
- `npm install js-yaml --save-prod`

 `yargs` module should be present once the repository is cloned. In case it throws an error for yargs module, please run the following command:
 - `npm install --save @types/yargs`
 
 `fs-extra` module should be present. In case it throws an error, please run the following command:
 - `npm install fs-extra`

#### Operating System Dependency:
Please run the following command from DEVOPS-06 directory
- `dos2unix pipeline/run-ansible.sh`
- `dos2unix pipeline/server-init.sh`

This can also be alternative set permanently for each user/system/project:<br>
Per system solution:<br>
`git config --system core.autocrlf false` 
<br>Per user solution:           
`git config --global core.autocrlf false`
<br>Per Project solution:            
`git config --local core.autocrlf false`  

Verify if the changes have appplied by running the below in the working directory :<br>
`git config core.autocrlf`

### Pipeline Commands to run Milestone 2:
`npm install`

`node index.js init`

Provision and configure computing environment for pipeline:

`pipeline init`
  
Trigger a build job, running steps outlined by build.yml, wait for output, and print build log:

`pipeline build mutation-coverage build.yml`
  
### Template for .env file:
<b>Create .env file in the DEVOPS-06 directory:</b>`touch .env`

`GIT_TOKEN=<YOUR_GIT_ACCESS_TOKEN>`<br>
`GIT_REPO=github.ncsu.edu/engr-csc326-staff/iTrust2-v10.git`<br>
`MY_SQL_PASSWORD=devops-06`<br>
`VM_IP=192.168.56.10`<br>
`VM_USER=vagrant`

<b>NOTE:</b> Please use your personal GIT Access Token in place of `<YOUR_GIT_ACCESS_TOKEN>`

### Main Tasks Completed in Milestone 2:
- Automation of dos2unix for windows
- build.yml modifications based on feedback from Milestone 1 evaluation
- Generate baseline snapshots
- Create test harness to generate snapshot from mutated code
- Compare snapshots using DOM-based or image-based difference
- Generate mutation coverage using test harness
- Remove secret variables from the display log
- Generating output logs and errors
- Mutation coverage calculation 

### Team Contirbution for Milestone 2:
- Working on modifications for M1 based on Feedback : Prithvish Doshi & Manvita Balachandra
- Generate baseline snapshots : Vijaya Durga Kona
- Create test harness to generate snapshot from mutated code : Prithvish Doshi and Vijaya Durga Kona
- Compare snapshots using DOM-based or image-based difference : Prithvish Doshi 
- Generate mutation coverage using test harness: Manvita Balachandra
- Remove secret variables from the display log: Vijaya Durga Kona and Manvita Balachandra
- Generating output logs and errors: Vijaya Durga Kona, Prithvish Doshi and Manvita Balachandra
- Mutation coverage calculation: Manvita Balachandra, Prithvish Doshi, Vijaya Durga Kona

### Learnings/Experiences in Milestone 2:
- Esprima and escodegen functionalities 
- ASTRewrite ast tree traversal for mutator automation
- build.yml automation to ensure plus and play of commands helps in extending the project to install any dependency
- snapshot generation 
- node-resemble-js functionalities and dependencies of resemble-js
- Importance of synchrozonization while generating multiple snapshots
- Mutation coverage calculation 

### Issues Faced in Milestone 2:
- Error: `pipeline is not recognised as an internal or external command`. The issue was resolved when we did `npm link`
- When the files were checked out in Windows ,`.sh` files were not recognised due to formatting issues. We used dos2unix command to avoid issues for the shell files.
- Indentation of Ansible scripts (mutation.yml file)
- Syncrhonization issue while calculating mutation coverage for multiple mutated snapshots simultaneously
- Esprima incremental, control statement and clone return mutations
- `ast` tree traversal and backtracking to point to necessary node attributes
- js-yaml and yargs issue when existing project directory is deleted and new pull is taken

### Screenshots of Execution for Checkpoint 2:

#### Linux System:
##### Pipeline init
<p align = "center">
<img width="900" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/Linux_M2_init.png">
</p>

##### iTrust Job
<p align = "center">
<img width="900" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/Linux_M2_itrust-build.png">
</p>

##### Mutation coverage job
<p align = "center">
<img width="900" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/Linux_M2_mutation-coverage.png">
</p>

#### Windows System:
##### Pipeline init
<p align = "center">
<img width="900" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/Windows_M2_init.png">
</p>

#### iTrust Job 
<p align = "center">
<img width="900" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/ItrustM2.PNG">
</p>


##### Mutation coverage job
<p align = "center">
<img width="900" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/Windows_M2_mutation-coverage-build.png">
</p>

### Project Board:

<p align = "center">
<img width=1200" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/Project-board-M2.PNG">
</p>

[View Project Board](https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/projects/2)

### Issue Board:

<p align = "center">
<img width="1000" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/Issue-board-M2.PNG">
</p>

[View Issue Board](https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/issues)

# Milestone 1 (Pipeline > Build)

### Project Team:

- Manvita Balachandra ( mbalach )
- Prithvish Rakesh Doshi ( pdoshi )
- Vijaya Durga Kona ( vkona )

### System Dependency for Milestone 1:
- Linux OS
- Windows OS
- MAC OS with Intel processor

### Project Specification for Milestone 1:

[View Project Specification](https://github.com/CSC-DevOps/Course/blob/master/Project/M1.md) 

### Steps to setup repository of Milestone 1:
- `git clone https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06.git`

- `cd DEVOPS-06`

- `npm install`

- `npm link`

### Pre-requisites needed to run Milestone 1:
`js-yaml` is a dependency that is installed automatically. In case `pipeline init` gives an error related to `js-yaml`, please run the following command:
- `npm install js-yaml --save-prod`

#### Operating System Dependency - Only for Windows users:
Please run the following command from DEVOPS-06 directory
- `dos2unix pipeline/run-ansible.sh`
- `dos2unix pipeline/server-init.sh`

### Pipeline Commands to run Milestone 1:
Provision and configure computing environment for pipeline:

`pipeline init`
  
Trigger a build job, running steps outlined by build.yml, wait for output, and print build log:

`pipeline build itrust-build build.yml` 
  
### Template for .env file:
<b>Create .env file in the DEVOPS-06 directory:</b>`touch .env`

`GIT_TOKEN=<YOUR_GIT_ACCESS_TOKEN>`<br>
`GIT_REPO=github.ncsu.edu/engr-csc326-staff/iTrust2-v10.git`<br>
`MY_SQL_PASSWORD=devops-06`<br>
`VM_IP=192.168.56.10`<br>
`VM_USER=vagrant`

<b>NOTE:</b> Please use your personal GIT Access Token in place of `<YOUR_GIT_ACCESS_TOKEN>`

### Main Tasks Completed in Milestone 1:
- Provision a project-server with Ubuntu `focal` 20.04 image using `bakerx`
- Preserve the details of the configured server in a file ( inventory.ini )
- Display the details of the configured server as output on the console
- Configure the build server ( project-server )
- Create a build job specification with setup, jobs heirarchy
- Install maven, jdk, java11, nodejs, wget, set debconf-utils. Set MySQL password and clone the git repository.
- Parse application.yml.template to application.yml to store correct details
- Run `cd iTrust2 && mvn --batch-mode --update-snapshots clean test`

### Team Contirbution for Milestone 1:
- Provision the build server to come up with ubuntu focal image, ip, username, private_key : Manvita Balachandra
- Create build.yml to install JDK, MySQL, Maven, JAVA11 : Prithvish Doshi
- Build a component to handle multiple jobs inside build.js : Vijaya Durga Kona
- Ensure .env file is accessible by playbook/js file locally and even on the build server : Vijaya Durga Kona & Manvita Balachandra
- Parsed the design hierarchy for execution of tasks in yaml file : Prithvish Doshi & Vijaya Durga Kona
- Automatically configured build environment : Manvita Balachandra & Prithvish Doshi & Vijaya Durga Kona
- Generate git access token : Manvita Balachandra
- Handle credentials and service state for MySQL : Vijaya Durga Kona & Prithvish Doshi
- Handled pre-cloning functions and set debconf-utils : Prithvish Doshi & Manvita Balachandra
- Cloned https://github.ncsu.edu/engr-csc326-staff/iTrust2-v10 repository to correct path : Vijaya Durga Kona
- Parsed application.yml.template file to application.yml : Prithvish Doshi
- Perform maven test on Windows : Vijaya Durga Kona
- Perform maven test on Linux : Prithvish Doshi
- Document the project details in README.md and record a screencast for demo : Manvita Balachandra

### Learnings/Experiences in Milestone 1:
- Provisioning a VM and accessing VM details
- Private key handling 
- Ansible script and its dependencies
- MySQL dependencies and checks while running on remote server
- Effect of time synchronization issues 
- Handling .env file variable declarations

### Issues Faced in Milestone 1:
- Error: `pipeline is not recognised as an internal or external command`. The issue was resolved when we did `npm link`
- When the files were checked out in Windows ,`.sh` files were not recognised due to formatting issues. We used dos2unix command to avoid issues for the shell files.
- Indentation of Ansible scripts (build.yml file)
- Figuring out descrepency with directory heirarchy: roles/setup/tasks Vs. roles/setup/jobs
- Coming up with own ansible readable file design to access files through the given file hierarchy as mentioned in project description
- Parsing our design for ansible to read them
- ntp time issues prevented us from executing maven tests
- Issue with sed command not being able to change the file contents in application.yml
- MySQL password issues on remote server (project-server)
- Accessing the .env variables in the code for server to read it without issues

### Screenshots of Execution for Checkpoint 1:

#### Windows System:
<p align = "center">
<img width="900" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/2M1.PNG">
</p>

<p align = "center">
<img width="900" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/1M1.PNG">
</p>

#### Linux System:

<p align = "center">
<img width="900" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/linux_init_result.png">
</p>

<p align = "center">
<img width="900" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/linux_build_successful.png">
</p>

### Project Board:

<p align = "center">
<img width=1200" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/Project-board-M1.PNG">
</p>

[View Project Board](https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/projects/1)

### Issue Board:

<p align = "center">
<img width="1000" alt="image" src="https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/Images/Issue-board-M1.PNG">
</p>

[View Issue Board](https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/issues)

### Screencast for Milestone 1:
[View Screencast](https://youtu.be/jHuGoz0y0QM)

### Checkpoint Report for Milestone 1:
[View CHECKPOINT-M1 Report](https://github.ncsu.edu/CSC-DevOps-S22/DEVOPS-06/blob/main/CHECKPOINT-M1.md)
