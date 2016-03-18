# mynewt_hc-sr04

A simple test library to connect a HC-sr04 ultrasonic distance sensor the mynewt core platform.

# Including in your mynewt project.

Add the following repository descriptor to your `project.yml` file

```
repository.mynewt_hc-sr04:
    type: github
    vers: 0-latest
    user: paulfdietrich
    repo: mynewt_hc-sr04
```

and include the following in your `project.repositories` variable

```
project.repositories:
    - apache-mynewt-core
    - mynewt_hc-sr04
```

Add the following dependency to your application's (or whatever uses this library) `pkg.yml` file.

```
```

