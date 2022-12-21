```sh
$ rm -f ~/.ckb-cli/keystore/*
$ echo 0000000000000000000000000000000000000000000000000000000000000001 > /tmp/foo
$ ckb-cli account import --privkey-path /tmp/foo
$ echo 0000000000000000000000000000000000000000000000000000000000000002 > /tmp/foo
$ ckb-cli account import --privkey-path /tmp/foo
```

```sh
$ rm -r data specs ckb-miner.toml ckb.toml default.db-options
$ ckb init --chain dev --ba-arg 0x75178f34549c5fe9cd1a0c57aebd01e7ddf9249e --ba-message 0xabcd
# ckb.toml 必须取消 block_assembler.notify 的注释, 否则 miner 会卡死
# ckb.toml 需要 rpc.modules 中增加 indexer 才能检查余额
$ pmname=ckbr pm c ckb run
$ pmname=ckbm pm c ckb miner
# 等待一段时间, 查看余额
$ ckb-cli wallet get-capacity --lock-arg 0x75178f34549c5fe9cd1a0c57aebd01e7ddf9249e
```
