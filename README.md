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

### Exercise set 2

1. Write out the steps for visiting the URL _/users/1/edit_.

    - On making the request _/users/1/edit_, the cooresponding _controller#action_ pair, according to the `rails routes` listing, is the `edit` method of the _users_ controller. Also, according to the URL template, the `id` of the user being edited is _1_.
    - First, however, the `before_action` method is called, which uses the `set_user` callback, to put the user's details, retreived using the user `:id`, into the `@user` instance variable. 
    - Since the `edit` method content is empty, the controller then renders a form using the view, `edit.html.erb`. The form is imported from the partial `_form.html.erb`. The existing user data is passed into the view, to pre-fill the form fields, using the `@user` variable.
    - The rendered HTML is sent by the controller to the client browser.

    **On form submission**

    - The new information is sent to the server using the HTTP PATCH method, using the URL format _/users/1_ which then calls the `update` method of the _users_ controller.
    - If the update was successful, then the `show` action is executed and the new user details are displayed using the _/users/1_ URL, along with the notice message _User was successfully updated._
    - If the update failed, the edit page is displayed again with error messages.

2. Find the line in the scaffolding code that retrieves the user from the database in the previous exercise.

    - This is line number 2, of the _users_controller.rb_: `before_action :set_user, only: [:show, :edit, :update, :destroy]`

3. What is the name of the view file for the user edit page?

    - It's `app/views/users/edit.html.erb`