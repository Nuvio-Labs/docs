---
sidebar_position: 1
---

# Welcome to the Acadea Developer Documentation

This documentation is intended for developers who want to work directly with the Acadea API. If you are a Acadea administrator or instructor, please refer to the [Acadea Help Center](https://help.Acadea.io).

## What is the Acadea API?

The Acadea API is a RESTful API that allows you to interact with Acadea programmatically. You can use the API to create, read, update and delete Acadea resources such as courses, modules, assignments, assessments, users, etc.

## How do I get started?

First, you must log into your already existing Acadea account. If you don't have an account, please contact your administrator.

Once you are logged in, you will be presented with the Acadea dashboard. The dashboard is the main page of Acadea and it is where you can access all of your Acadea features.

From there you will need to create a new account for your application. API accounts are just administrative accounts that are used to interact with the API. They are not meant to be used by actual users. To create a new API account, go to the "Users" tab on the top of the dashboard. On the Accounts page, click the "Create Account" button. You will be presented with a form where you can enter the details of your account. Once you are done, click the "Create Account" button.

## Logging in to the API

To log into the API for your specific organization, you will need to use the credentials of the API account you created. From there, connect to the API using the following URL: `[your organization].Acadea.io/api/`. For example, if your organization is called "My Organization", you will need to connect to `myorganization.Acadea.io/api/`.

Once you are connected to the API, you will need to authenticate using the API account credentials. To do so, you will need to send a POST request to the `/api/auth/login` endpoint. The request body should contain the following JSON:

```json
{
  "email": "<your API account email>",
  "password": "<your API account password>"
}
```

By default, the API will return a JSON response that contains authentication details. You can use these details to authenticate future requests. For example, you can use the `token` to authenticate requests using the `token` header. This token is valid for 7 days. After 7 days, you will need to either log in again or refresh the token using the already provided refresh token and `/api/auth/refresh` endpoint.

To verify that you are logged in, you can send a GET request to the `/api/auth/verify` or `/api/users/@me` endpoints. Both of these endpoints will return the details of the currently logged in user.

```rest
GET /api/auth/verify
```
```json
{
	"user": {
		"avatar": "https://www.gravatar.com/avatar/00000000000000000000000000000000?d=mp&f=y",
		"dob": "",
		"email": "tsmith@test.com",
		"id": "user:hzrpck4ts0i7s27xgwsn",
		"name": "Timothy Smith",
		"role": "staff"
	},
	"exp": 1682040039
}
```

## API Resources

The Acadea API allows you to interact with the following resources:

- Courses
- Assignments
- Assessments
- Modules
- Resources
- Users


## API Reference

The API reference is currently a work in process. Please stay tuned for updates.