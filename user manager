class UserManager:
    __instance = None

    def __new__(cls, *args, **kwargs):
        # Singleton pattern to ensure only one instance of UserManager
        if cls.__instance is None:
            cls.__instance = super().__new__(cls)
        return cls.__instance

    def __init__(self) -> None:
        if not hasattr(self, "__initialized"):
            self.__initialized = True
            self.users = dict()

    def add_user(self, name):
        """Add a new user to the system."""
        if name not in self.users:
            self.users[name] = {}
            print(f"User with name {name} added")

    def add_user_data(self, user_name, *args, **kwargs):
        """Add data to an existing user."""
        if user_name not in self.users:
            print(f"User with name {user_name} not found")
            return
        d = {}
        for item in args:
            try:
                k, v = item.split("=")
                d[k] = v
            except ValueError:
                print(f"Incorrect data format: {item}")
        if d or kwargs:
            self.users[user_name].update(d)
            self.users[user_name].update(kwargs)
            print("User data added")

    def user_change_data(self, user_name, *args, **kwargs):
        """Change data of an existing user."""
        if user_name not in self.users:
            print(f"User with name {user_name} not found")
            return
        d = {}
        for item in args:
            try:
                k, v = item.split("=")
                d[k] = v
            except ValueError:
                print(f"Incorrect data format: {item}")
        if d or kwargs:
            self.users[user_name].update(d)
            self.users[user_name].update(kwargs)
            print("User data updated")

    def get_user_data(self, user_name, key=None):
        """Retrieve user data. Optionally provide a key."""
        if user_name in self.users:
            if key is not None and key in self.users[user_name]:
                return self.users[user_name][key]
            elif key is not None:
                return f"Key {key} not found for user {user_name}"
            else:
                return self.users[user_name]
        else:
            return f"User with name {user_name} not found"

    def del_user(self, user_name):
        """Delete a user from the system."""
        if user_name in self.users:
            del self.users[user_name]
            print(f"User with name {user_name} removed from the list")
        else:
            print(f"Failed to remove user {user_name}")

    def del_user_data(self, username, key=None):
        """Delete data from a user. Optionally provide a key."""
        if username in self.users:
            if key is not None and key in self.users[username]:
                del self.users[username][key]
                print(f"User data for {username} with key {key} was removed")
            else:
                print(
                    f"User data for {username} with key {key} not found or key not provided"
                )
        else:
            print(f"User with name {username} not found")
