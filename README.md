# fp-patterns

## command

```typescript
//typescript code 
interface ICommand {
  execute: () => void;
}

const DB = {
  login: (user: string, password: string) => {
    console.log("login", user, password);
  },
  logout: (user: string) => {
    console.log("logout", user);
  }
};

class LoginCommand implements ICommand {
  private user: string;
  private password: string;

  constructor(user: string, password: string) {
    this.user = user;
    this.password = password;
  }

  public execute() {
    DB.login(this.user, this.password);
  }
}

class LogoutCommand implements ICommand {
  private user: string;

  constructor(user: string) {
    this.user = user;
  }

  public execute() {
    DB.logout(this.user);
  }
}

new LoginCommand("django", "unCh@1ned").execute();
new LogoutCommand("django").execute();

```

```typescript
((user: string, password: string) => {
  console.log("login", user, password);
})("django", "unCh@1ned");

((user: string) => {
  console.log("logout", user);
})("django");
```

