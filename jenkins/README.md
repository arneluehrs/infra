Jenkins for Devops Dojo
=================

This Jenkins image is based on top of the [official Jenkins image][official-jenkins] and as such provides all its features.
Additionally, it comes with the **[Github Oauth plugin][github-oauth-plugin] ready to use**.


How to run
-----

    docker-compose up -d


What does it do?
----------------

When you start the container the following happens:

1. The image comes with all plugins installed (plugins.txt)
2. Jenkins starts
3. Groovy scripts defined in Dockerfile are executed
4. Authentication is setup to use Github Authentication


Included plugins
----------------

- [Github Oauth plugin][github-oauth-plugin]
- [Git][git]
- [GitHub][github]

Plugins coming soon
----------------

- [GitHub pull request builder][ghprb]
- [Pipeline][workflow-aggregator]


Customizing the image
-----

### Presteps
    
    [Setup Docker] [docker]
    [Create a developer app in Github] [github-oauth-plugin]
    [Setup Git] [git]

### Steps

    docker build -t your_user/jenkins:0.0.1 .
    docker tag your_user/jenkins:0.0.1 chavomar/jenkins:latest
    docker run -d -p 80:8080 your_user/jenkins:0.0.1



[official-jenkins]: https://github.com/jenkinsci/docker/blob/master/README.md
[github-oauth-plugin]: https://github.com/jenkinsci/github-oauth-plugin
[git]: https://git-scm.com/
[docker]: https://docs.docker.com/

[docker-rm]: https://docs.docker.com/reference/commandline/rm/
[docker-workflow]: https://wiki.jenkins-ci.org/display/JENKINS/CloudBees+Docker+Pipeline+Plugin
[ghprb]: https://wiki.jenkins-ci.org/display/JENKINS/GitHub+pull+request+builder+plugin
[git]: https://wiki.jenkins-ci.org/display/JENKINS/Git+Plugin
[github]: https://wiki.jenkins-ci.org/display/JENKINS/GitHub+Plugin
[init.groovy.d]: https://wiki.jenkins-ci.org/display/JENKINS/Configuring+Jenkins+upon+start+up
[job-dsl]: https://wiki.jenkins-ci.org/display/JENKINS/Job+DSL+Plugin
[warnings]:  https://wiki.jenkins-ci.org/display/JENKINS/Warnings+Plugin


