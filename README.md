# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

## Answers

### Exercise set 1

1. Determine the CSS id for the text “User was successfully created.” What happens when you refresh your browser?

    - The id is `notice`. On refreshing the page, the `#notice` element has no content, though the element remains a part of the page.

2. What happens if you try to create a user with a name but no email address?

    - The user is successfully created.

3. What happens if you try create a user with an invalid email address, like “@example.com”?

    - The user is successfully created.

4. Destroy each of the users created in the previous exercises. Does Rails display a message by default when a user is destroyed?

    - Message displayed is _User was successfully destroyed._ 