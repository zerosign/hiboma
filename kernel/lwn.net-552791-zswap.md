# lwn.net: zswap: compressed swap caching

 * http://lwn.net/Articles/552791/

## 斜め訳

 * v3.11 から
 * ___memory compression___

``` 
Useful References:

LSFMM: In-kernel memory compression
https://lwn.net/Articles/548109/

The zswap compressed swap cache
https://lwn.net/Articles/537422/
```

## zswap

swap page の圧縮

 * プロセスの swapout されるページを、動的に確保されたRAMのメモリプールにいれとく
   * 成功すると swap device への writeback を遅延、もしくは 防ぐことができる
   * swap するシステムでめっちゃ I/O 減らせる

ベンチマーク

 * 53% の runtime reduction
 * 76% の I/O reduction