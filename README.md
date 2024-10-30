# Neo4j CLI

## Installation

Downloadable binaries are available from the [releases](https://github.com/neo4j/cli/releases/latest) page.

## Development

### Testing

The full suite of tests can be run using the following command:

```bash
go test ./...
```

### Local running

The CLI can be run locally without building by running the following command:

```bash
go run neo4j-cli/main.go
```

### Pull requests

As well as your code changes, pull requests need a changelog entry. These are added using the tool [`changie`](https://changie.dev/). You will need to install this using the following command:

```bash
go install github.com/miniscruff/changie@latest
```

With this installed, the following command will guide through the process of adding a changelog entry:

```bash
changie new
```

Simply commit the file that this command produces and you're done!

### Building

Builds for releases are handled in GitHub Actions. If you want to create local builds, there are a couple of approaches.

To create a simply binary using `go` directly, you can execute the following command:

```bash
go build -o bin/ ./...
```

If you want to build binaries for all varieties of platforms, you can do so with the following command:

```bash
GORELEASER_CURRENT_TAG=dev goreleaser release --snapshot --clean
```

In the above command, `GORELEASER_CURRENT_TAG` can be substituted for any version of your choosing.
