# RBAC and Authentication Mini-App

This Python script demonstrates a simulated login and role-based access control
(RBAC). It uses Python's standard features and does not need extra packages.

## Run the app

Install Python 3, open this folder in VS Code, and run this command in the terminal:

```bash
python app.py
```

On Windows, you can also use `py app.py` if the `python` command is unavailable.
The script runs automatically without asking for a username or password.

## Authentication and access control

Authentication answers, "Who are you?" Here, `login()` simulates this by checking
a hardcoded username against the `USERS` dictionary. A known account with a
supported role logs in successfully; an unknown account fails and returns `None`.

Authorization answers, "What are you allowed to do?" After login, each protected
function checks the account's role with `has_role()` before showing its content.
Roles come from the dictionary rather than user input. Accounts without a valid
role are denied access.

| Hardcoded username | Role | Admin action | User action |
| --- | --- | --- | --- |
| sherlyn_admin | admin | Allowed | Denied |
| sherlyn_user | user | Denied | Allowed |
| unknown_account | Login fails | Denied | Denied |

`admin_action()` simulates viewing an internal administration report.
`user_action()` simulates opening a user dashboard. As required by this assignment,
the roles are exclusive: admins cannot access the user-only action.

## CIA triad

The CIA triad consists of **Confidentiality**, **Integrity**, and **Availability**.
Confidentiality restricts information to authorized people. Integrity protects
information from unauthorized changes. Availability means authorized people can
access systems and information when needed.

This app demonstrates **confidentiality**. The admin report is displayed only
when the logged-in account has the admin role. A regular user or an account that
failed login receives an access-denied message without seeing the report.
The user dashboard is also restricted to its required role. Checking permission
inside each action helps keep the restriction in place whenever it is called.

## Demonstration and expected results

The script attempts login as an admin, a user, and an unknown account. It tries
both actions after every attempt so you can see successful access and denials.
There should be two access-granted messages, four access-denied messages, two
successful logins, and one failed login.

## Simulation limits

The assignment requests hardcoded usernames and roles without passwords or form
input. This is a classroom simulation, not production authentication: a username
alone does not prove identity. A real application would need identity verification
and protected sessions in addition to authorization checks. All displayed data in
this demonstration is fictional.
