```go
func x(y [3]int) {
	y[2] = 3
}
func main() {
	s := [3]int{1, 3}
	x(s)
	fmt.Println(s)
}```
result is  [1 3 0] so `Golang` is #PassByValue