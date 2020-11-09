# Deployment Information

## Maven Central
Group ID: **com.graphqlio**

## PGP 
Signature Key: tbd
Local location: **%USER_HOME%/.gnupg**

## Maven
1. **Settings.xml**
Local location: **%USER_HOME%/.m2**
Contains information about maven central server access and pgp signature

2. **pom.xml**
Every pom.xml from every GraphQL IO project is usable as template (e.g. [pure-uuid](https://github.com/msg-systems/pure-uuid-java/blob/master/pom.xml)).
> Noteable content:
> - org.sonatype.plugins
> - Deploy profile: Compiles, builds JavaDoc and signs the artefacts
> - DistributionManagement: Defines repositories for release artefacts
> - SCM: Connection infos for source code VCS (github repository)

3. **Commands**
Local deploy: **mvn clean deploy -P deploy**

## Github
GithubAction: We use Github Actions for auto deployment. The deployment will be triggered when a tag is pushed. Every GraphQL IO project contains this Github action and can be used as template.
> Note: Secrets have to be set for the actions.
> - GPG_PASSPHRASE
> - GPG_PRIVATE_KEY
> - NEXUS_USERNAME
> - NEXUS_PASSWORD