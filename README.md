# FortNynja Backend Assignment

## Assignment Requirements

### Overview

- An API-only Ruby-on-Rails application with SQLite as the database.

### User model

- The current project has a `devise` User model. Please use this as the basis for the authentication framework.
- Create two (2) roles for the user model: `CompanyUser` and `Moderator`.
- Both `CompanyUser` and `Moderator` have the following data model:
  - First name (string)
  - Last name (string)
  - Email (string)
  - Created/Updated at (timestamp)
  - Created/Updated by (user ID)

### Bounty model

- A `Bounty` has:
  - Title (string)
  - Description (string)
  - Status (pending/approved/rejected)
  - Created/Updated at (timestamp)
  - Created/Updated by (user ID)

### Company model

- A `Company` has:
  - Name (string)
  - Address (string)
  - Website URL (string)
  - Created/Updated at (timestamp)
  - Created/Updated by (user ID)

### Associations

- A `CompanyUser` can only have one `Company`.
- `CompanyUser` can create many `Bounties`.
- `Moderator` can create `CompanyUser` and `Company`, but not `Bounty`.
- Only a `Moderator` can approve or reject a `Bounty`.
- Only approved bounties are publicly viewable. `Moderator` can view all bounties.
- Approved bounties can be filtered based on companies.

### Tests

- Please add some automated test scenario that makes sense to you. We use `rspec` but you may choose any framework that works for you.

### (Optional) Extra integration

- If you're up for the challenge:
  - Migrate from SQLite to PostgreSQL
  - Integrate automated API documentation (OpenAPI is preferred)
  - Dockerize the application
  - Host your application on the cloud (eg. Heroku)

### Other Notes

- **Clone** the repo (not fork) to a private repository to get started. Please don't push everything in one commit. We would love to see how you structure your commits.
- Don't feel like you have to stay within the placeholder files. If you want to create some helper/utility functions, go ahead and create the appropriate file/folders for that.
- Feel free to use any tool, library or tune the project (including the setup files) to fit your needs. The only requirements are to use `rails` and `devise`.
- If you are unclear about something or want to run something by the team, please feel free to reach out. We like to get a sense of how you would work/collaborate on a real task.
- Send us over the GitHub URL when you are complete so we can check it out!

---

## Project Setup

### System dependencies

- Ruby 3.1.2
- Rails 6.1.5

### Login to get access token

`curl -X POST -d "grant_type=password&email=user@example.com&password=yourpassword" localhost:3000/oauth/token`

### Using your endpoints

`curl -v localhost:3000/users?access_token=OurAccessTokenReturnedByAPI`
