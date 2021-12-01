# sample project for pprof-nodejs with express (TypeScript)

## Usage

### Install

```sh
n auto
npm i
```

### Launch server

```sh
npm run build
npm run start
```

### Benchmark

```sh
curl -X GET 'http://localhost:8080/newUser?username=matt&password=password'
ab -k -c 20 -n 250 'http://localhost:8080/auth?username=matt&password=password'
```

### Analyze the profiling result

```sh
# download pprof
go get -u github.com/google/pprof

# view result
pprof -http=: wall.pb.gz
# or ~/go/bin/pprof -http=: wall.pb.gz
```

## Note

- it requires `Long` type support
  - so this project depends on the `long` and `@types/long` packages
  - and configure the `types` to support the `long` in [tsconfig.json](./tsconfig.json)

## References

- <https://github.com/google/pprof-nodejs>
- <https://nodejs.org/ja/docs/guides/simple-profiling/>
