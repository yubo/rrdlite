# Go (golang) for rrdtool(1.4.9)

一个轻量级的rrdtool工具包，线程安全，解除librrd依赖,只提供create,update,fetch,info

## Installing

    go get github.com/yubo/rrdlite

## Benchmark
```shell
#enable mmap
$go test -bench=Add
#or
$go test -bench=.

...
#cgo CFLAGS: -std=c99 -DRRD_LITE -D_BSD_SOURCE -DHAVE_CONFIG_H -D_POSIX_SOURCE -DNUMVERS=1.4009
BenchmarkAdd-4            100000             49386 ns/op
BenchmarkUpdate-4         100000             19366 ns/op
BenchmarkFetch-4          100000             10956 ns/op

#cgo CFLAGS: -std=c99 -DRRD_LITE -D_BSD_SOURCE -DHAVE_CONFIG_H -D_POSIX_SOURCE -DNUMVERS=1.4009 -DUSE_STDIO=1
BenchmarkAdd-4            100000             56381 ns/op
BenchmarkUpdate-4         100000             21609 ns/op
BenchmarkFetch-4          100000             17339 ns/op

#cgo CFLAGS: -std=c99 -DRRD_LITE -D_BSD_SOURCE -DHAVE_CONFIG_H -D_POSIX_SOURCE -DNUMVERS=1.4009 -DHAVE_MMAP
BenchmarkAdd-4            100000             50000 ns/op
BenchmarkUpdate-4         100000             13741 ns/op
BenchmarkFetch-4          100000             11005 ns/op
```


## Example 
See [rrd_test.go](https://github.com/yubo/rrdlite/blob/master/rrd_test.go) for an example of using this package.
