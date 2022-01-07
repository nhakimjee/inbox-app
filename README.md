# Inbox Application
Spring Boot project using OAuth login with GitHub and Cassandra

Steps:
1. Create a GitHub App and get the Client ID and Client Secret values. (Specify callback URL as `http://localhost:8080/login/oauth2/code/github` for development, uncheck Web hooks)
2. Add those values in `application.yml`
3. Run the Spring Boot App. You should be able to login with GitHub

Post login, you will be redirected back to the login page, but you can validate the authorized principal is created by accessing the `/user` API. 

Spring Data Configuration:
1. Generate client token for Datastax
2. Substitute clientId for spring.data.cassandra.username
3. Substitute clientSecret for spring.data.cassandra.password

Datastax Database Configuration
1. Set values for astra.db as follows:
   1. id from db clusterId
   2. reqion from db region
   3. keyspace from the db keyspace
   4. application.token from client token generated above

2. Download secure-connect.zip for the datastax db from the connect tab
   to the resources folder
3. Put the secure connect bundle in the .gitignore so that it is not in github
