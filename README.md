# Cloud Config Management Tool
[![Build Status](https://travis-ci.org/internnn/nextlinker_cmdb.svg?branch=master)](https://travis-ci.org/internnn/nextlinker_cmdb)

It's a project assigned by supervisor in MS team and was developed by intern partners and me during my internship. This CMDB enables MS and SA colleagues to validate, deploy the infra automatically, and it supports version control, tracking and a system to notify and ask for approval of deployment. Moreover, combined with `terraformer` and `ansible tower`, it is able to manage existing infra of cross-account clients.
Since the internship is ended, my AWS access key, secret key and autorities are disabled; hence this CMDB is not working now. However, perhaps this project will continue to be developed and help enhance their workflow and procedure.

## Project Structure

![](https://github.com/nathanjonjon/CMDB_project/blob/master/structure.png)


## How it works

1. Use Terraformer to generate `.tf` codes of specified infra

2. Pushing the files to GitHub triggers Travis CI and complete validation automatically

3. Travis CI informs AWX by webhook

4. In AWX, playbooks creates golden AMIs of our infra, save tfstate files to S3 and deploy the infra automatically.
