# fp-patterns

##command

```typescript
//typescript code 
class LoginCommand implements Command {

  private String user;
  private String password;

  public LoginCommand(String user, String password) {
    this.user = user;
    this.password = password;
  }

  @Override
  public void execute() {
    DB.login(user, password);
  }
}

public class LogoutCommand implements Command {

  private String user;

  public LogoutCommand(String user) {
    this.user = user;
  }

  @Override
  public void execute() {
    DB.logout(user);
  }
}

(new LoginCommand("django", "unCh@1ned")).execute();
(new LogoutCommand("django")).execute();
```

```typescript
//typescript code 
(defn execute [command]
  (command))

(execute #(db/login "django" "unCh@1ned"))
(execute #(db/logout "django"))
```

