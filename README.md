# go-graphql-mongodb
The Go Job-Listing-Board project integrates GraphQL and MongoDB. The application leverages GraphQL to communicate with the MongoDB database, which serves as the primary data storage for the job listings. The GraphQL API provides a flexible and efficient way for users to query and manipulate job listings data.

# Steps to run
1. Clone the git repo
```
git clone https://github.com/zigbee-s/go-graphql-mongodb.git
```

2. Add your mongoDb URI connection string in the database/datbase.go file

3. Run the code using: 
```
go run server.go
```

# GraphQl queries

## Get All Jobs
query GetAllJobs{ jobs{ _id title description company url } }

=======================

## Create Job
mutation CreateJobListing($input: CreateJobListingInput!){ createJobListing(input:$input){ _id title description company url } }

Variables:

{ "input": { "title": "Software Development Engineer - I", "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt", "company": "Google", "url": "www.google.com/" } }`

=========================

## Get Job By Id
query GetJob($id: ID!){ job(id:$id){ _id title description url company } }

Variables:

{ "id": "638051d7acc418c13197fdf7" }

=========================

## Update Job By Id
mutation UpdateJob($id: ID!,$input: UpdateJobListingInput!) { updateJobListing(id:$id,input:$input){ title description _id company url } }

Variables:
{ "id": "638051d3acc418c13197fdf6", "input": { "title": "Software Development Engineer - III" } }

=================================

## Delete Job By Id
mutation DeleteQuery($id: ID!) { deleteJobListing(id:$id){ deletedJobId } }

Variables:
{ "id": "638051d3acc418c13197fdf6" }