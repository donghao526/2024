Golang中Channel，可以用for range来遍历，发送方可以通过close一个channel来高速接收方没有更多的数据要发送

参考：https://go.dev/tour/concurrency/4
> A sender can `close` a channel to indicate that no more values will be sent. Receivers can test whether a channel has been closed by assigning a second parameter to the receive expression: after

> ```
> v, ok := <-ch
> ```

> `ok` is `false` if there are no more values to receive and the channel is closed.

> The loop `for i := range c` receives values from the channel repeatedly until it is closed.
```
## 做一个Test
```
```Go
func main() {
    c := make(chan int)

    // Start a goroutine to send values to the channel
    go func() {
    // Use range to iterate over the values in the channel
        for i := range c {
            fmt.Println(i)
        }
    }()

    for i := 0; i < 5; i++ {
        c <- i
    }
    close(c)
}
```

```shell
16:09:46 ~/leetcode $ go run main.go
0
1
2
3
4
```
