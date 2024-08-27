# User Manager

A Python class implementing a simple user management system using the Singleton design pattern. The `UserManager` class allows you to add, update, retrieve, and delete user information.

## Features

- Add new users
- Add and update user data
- Retrieve user data
- Delete users and user data
- Singleton pattern to ensure only one instance of the UserManager

## Usage

```python
from user_manager import UserManager

# Create an instance of UserManager
users = UserManager()

# Add users
users.add_user("alice")
users.add_user("bob")

# Add data to users
users.add_user_data("alice", "age=25")
users.add_user_data("bob", "email=bob@example.com")

# Update user data
users.user_change_data("alice", "age=26")

# Retrieve user data
print(users.get_user_data("bob", "email"))

# Delete user data
users.del_user_data("alice", "city")

# Delete a user
users.del_user("bob")
