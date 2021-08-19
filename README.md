# Hermes

Hermes is a simple library for React that makes working with axios really simple. Hermes provides a hermes class which can be used for configuration, hooks and a general method which can be used from anywhere in your app.

*Hermes has a 100% TypeScript support as it was created with TypeScript.*

## Hermes Class

The hermes class is used for configuring hermes to behave in a specific way. The available options are:

* baseUrl: string  "";

* token: string = "";

* parseErr: boolean = true;

* blockOffline: boolean = true;

* onAuthError: Function;

* onServerError: Function;

### hermes

Request allows you to quickly make a hermes request...

## Hooks

Hermes comes with react hooks which come with a lot more functionality like background refreshes.

### useHermes

useHermes is the most the most basic hermes hook, as all other hooks are based on it. You can make a request like this.

```tsx
const FetchUsers = () => {
  const [res, loading, error] = useHermes("/users");

  const users = res?.data?.data?.users;

  return loading ? <Loader /> : (
    <div>
      {error && <Error err={error} />}
      {users && <Users data={users} />}
    </div>
  );
};
```
