---
title: "First_post"
date: 2022-06-18T15:41:39+08:00

tags: ["abc","efd"]
categories: ["aaaaa"]
---

# my first_post

```go
package main

import (
	"strconv"

	"github.com/gofiber/fiber/v2"
	"github.com/gofiber/fiber/v2/middleware/logger"
	"github.com/gofiber/fiber/v2/middleware/recover"

	// _ "github.com/mattn/go-sqlite3"

	"github.com/Vulpecula1660/fiber-natours/api"
	"github.com/Vulpecula1660/fiber-natours/api/protocol"
	"github.com/Vulpecula1660/fiber-natours/enum"
)

func main() {
	app := fiber.New(fiber.Config{
		// Override default error handler
		ErrorHandler: func(ctx *fiber.Ctx, err error) error {
			// Return from handler
			if customError, ok := err.(*enum.CustomError); ok {
				return ctx.Status(customError.HTTPStatus).JSON(protocol.Response{
					Code:    strconv.Itoa(customError.Code),
					Message: customError.Message,
					Result:  struct{}{},
				})
			}
			return ctx.Status(fiber.StatusInternalServerError).JSON(protocol.Response{
				Code:    "99999",
				Message: "error",
				Result:  struct{}{},
			})
		},
	})

	app.Use(logger.New())

	app.Use(recover.New(recover.Config{
		EnableStackTrace: true,
	}))

	api.SetupRoutes(app)

	// client, err := ent.Open("sqlite3", "file:ent?mode=memory&cache=shared&_fk=1")
	// if err != nil {
	// 	log.Fatalf("failed opening connection to sqlite: %v", err)
	// }
	// defer client.Close()
	// // Run the auto migration tool.
	// if err := client.Schema.Create(context.Background()); err != nil {
	// 	log.Fatalf("failed creating schema resources: %v", err)
	// }

	app.Listen("127.0.0.1:3000")
}
```