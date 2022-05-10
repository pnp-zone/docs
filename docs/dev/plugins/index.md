# Writing plugins

## Create a go plugin

A pnp-zone plugin is a go plugin exposing the following functions:

```go
import (
	"github.com/labstack/echo/v4"
	"github.com/myOmikron/echotools/worker"
	"github.com/pnp-zone/common/conf"
	"gorm.io/gorm"
)

func MigrationHook() func(db *gorm.DB) error
func RouterHook() func(e *echo.Echo, db *gorm.DB, config *conf.Config) error
func StaticFileHook() (string, string)
func WorkerPoolHook() func(wp worker.Pool) error
```

To compile a go project make sure it contains a main package as plugin and run:
```bash
go build -buildmode=plugin -o <name>.so <name>
```

## Installing plugins

1. Put your `<name>.so` into the plugins directory defined in your server's config.
2. Put your plugin's static files under `plugins/<name>/` inside your server's `static` directory.

## Explaining the hooks

### StaticFileHook

This function is called during loading and returns the plugin's javascript and css (in this order) file to load.

The path's are resolved relative to the plugin's static directory (See Installing 2nd)

See [Javascript API](./js.md) for information on this javascript file.

