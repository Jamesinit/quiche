# 注意

## exapmple CS无法联通问题

当运行example目录下的,client和serve时。
如何server指定的地址是`./server 127.0.0.1 9988`可能会出现无法联通的情况，这时候需要将`127.0.0.1`替换为`0.0.0.0`

## Cargo run example 时Panic问题

错误log类似：

```log

thread 'main' panicked at 'called `Result::unwrap()` on an `Err` value: TlsFail'

```

原因是因为，你当前的目录并不在与example同级别路径，但是代码中需要读取`exapmle/cert.crt`.
切换到与example同级别的路径中即可。

## Cargo run 时注意 增加feature

`cargo run --features dtp,ffi --example server`

feature要加在前面，加在example之后不管用
