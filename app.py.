"""Demonstrate simulated login and role-based access control (RBAC)."""

# Hardcoded accounts for this classroom simulation; no password input is needed.
USERS = {
    "sherlyn_admin": "admin",
    "sherlyn_user": "user",
}


def login(username):
    """Simulate authentication by checking a known username and valid role."""
    if USERS.get(username) not in ("admin", "user"):
        print("Login failed: unknown username or unsupported role.")
        return None
    print(f"Login successful: {username} (role: {USERS[username]})")
    return username


def has_role(current_user, required_role):
    """Deny access unless the account exists and has the exact required role."""
    return current_user in USERS and USERS[current_user] == required_role


def admin_action(current_user):
    """Only admins may view the simulated confidential administration report."""
    if not has_role(current_user, "admin"):
        print("Access denied: admin role required.")
        return False
    # Confidentiality: this report is shown only after checking the admin role.
    print("Access granted: admin report - Internal account summary.")
    return True


def user_action(current_user):
    """Only users may open the simulated user dashboard, including no admins."""
    if not has_role(current_user, "user"):
        print("Access denied: user role required.")
        return False
    print("Access granted: user dashboard - Welcome to your account.")
    return True


def main():
    """Show allowed and denied actions for both roles and an invalid login."""
    print("RBAC and Authentication Mini-App")
    for username in ("sherlyn_admin", "sherlyn_user", "unknown_account"):
        print(f"\n--- Login attempt: {username} ---")
        current_user = login(username)
        admin_action(current_user)
        user_action(current_user)


if __name__ == "__main__":
    main()
