```go
package main

import (
	"fmt"
	"time"
)

func main() {
	tunnelToSenior := make(chan string)
	experienceHour := 3258
	developingHourForDay := 9

	go func() {
		for experienceHour < 15000 {
			for i := 0; i < developingHourForDay; i++ {
				time.Sleep(time.Hour * 1)
				experienceHour++
			}
			time.Sleep(time.Hour * 15)
		}
		tunnelToSenior <- "I'm senior Programmer"
	}()

	go func() {
		for {
			fmt.Println("Make code easier to understand everyone")
			fmt.Println("Work Hard, Play Hard")
			fmt.Println("Everything is up to mind")
		}
	}()

	sayLoud := <-tunnelToSenior
	fmt.Println(sayLoud)
	fmt.Println("Keep going...")
}
```
