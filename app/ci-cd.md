# CI CD Jenkins -> AWS

This projects shows building a continous integration and development server hosted using Amazon Web Services, using a previous HTML + JavaScript project.

## Demo

The demo shows that when an update occurs on the feature branch, on push it triggers the building of the first Jenkins then if that is succesful it will update
the second build which is the one for deployment.

![GIF showing command](./Demo.gif)

---

## How have you use Jenkins to add Continuous integration with this project?

Using CI/CD the integrations was automated through Jenkins by linking the project GitHub to the Jenkins service.
The project has a feature-branch that, whenever pushed on the GitHub repository, builds the project only if 
successful (by passing the tests defined in the project).

### How did you allow Jenkins access to the Github repo?

Jenkins is allowed access to the GitHub Repository by firstly, linking it using a web-hook and passing in the necessary
public key-private key thus ensuring the connection between the two can be made.

### How did you get the Github repo to trigger the build?

Jenkins was configured so that when changes are pushed to the feature-branch, a build construction will be triggered which 
will check if the build is succesful and if so it will push the changes to the main branch.

---

## How have you used Jenkins to add Continuous delivery with this project?

Continous delivery was done using EC2 intance of the Amazon Web Services which is used to host the project on its servers by using a virtual
environment where the project is continously run. When a push action is done on the GitHub feature-branch branch and it succeds, a CD build will be
triggered to run.

### How did you allow Jenkins access to the EC2 instance?

The Jenkins configurations of the CD build was done so that it is linked with the EC2 instance by adding it to the EC2 security groups, then 
linking it using a public-private key connection.

### How did you get the CI project to trigger the CD build?

The CI build was configured so that when it is succesful, it will trigger the CD build to use those changes and update the deployment build .

---
