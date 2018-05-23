# jenkins-backup-all-job-configs
Mini guide on how to backup all jobs' `config.xml` files VERY QUICKLY

1. Fetch you Jenkins username & API token (Jenkins Dashboard -> your name dropdown (top right) -> Configure -> Show API Token)
2. Fetch list of all jobs from your jenkins server using jenkins API

```
curl -u UNAME:API_TOKEN "http://<JENKINS_URL>/api/json?tree=jobs\[name\]"
```

3. filter the response JSON for all job names
4. Iterate over all job names and execute following:

```
curl -s -u UNAME:API_TOKEN "http://JENKINS_URL/job/<JOB_NAME>/config.xml > <JOB_NAME>_config.xml
```
