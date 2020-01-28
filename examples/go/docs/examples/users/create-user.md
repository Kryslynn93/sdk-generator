package main

import (
    "fmt"
    "os"
    "github.com/appwrite/go-sdk"
)

func main() {
    var client := appwrite.Client{}

    client.SetProject("")

    var service := appwrite.Users{
        client: &client
    }

    var response, error := service.CreateUser("email@example.com", "password")

    if error != nil {
        panic(error)
    }

    fmt.Println(response)
}