# Monitor

Monitor middleware for [Fiber](https://github.com/gofiber/fiber) that reports server metrics, inspired by [express-status-monitor](https://github.com/RafalWilinski/express-status-monitor)

:warning: **Warning:** Monitor is still in beta, API might change in the future!

![](https://i.imgur.com/4NfRCDm.gif)

## Table of Contents

* [Signatures](monitor.md#signatures)
* [Examples](monitor.md#examples)
* [Config](monitor.md#config)
* [Default Config](monitor.md#default-config)


### Signatures
```go
func New() fiber.Handler
```

### Examples
Import the middleware package and assign it to a route.
```go
package main

import (
	"log"

	"github.com/gofiber/fiber/v2"
	"github.com/gofiber/fiber/v2/middleware/monitor"
)

func main() {
	app := fiber.New()
	
	app.Get("/dashboard", monitor.New())
	
	log.Fatal(app.Listen(":3000"))
}
```

## Config

```go
// Config defines the config for middleware.
type Config struct {
	// Next defines a function to skip this middleware when returned true.
	//
	// Optional. Default: nil
	Next func(c *fiber.Ctx) bool
}
```

## Default Config

```go
var ConfigDefault = Config{
	Next: nil,
}
```