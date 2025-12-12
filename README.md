
Start the debugger in surfpool by passing the required ENV's to the litesvm -> bpf-loader -> sbpf

```bash
VM_DEBUG_PORT=6612 VM_DEBUG_EXEC_INFO_FILE=/tmp/gimlet_vm_info.txt surfpool-fork start
```


To install the surfpool-cli locally after you have cloned use 

```bash
cargo surfpool-install
```

It wil install the surfpool in `~/.cargo/bin/surfpool-fork` and u can use with `surfpool-fork` without overriding your original surfpool which should be inside `/opt/homebrew/bin/surfpool`



## Debugging

Use the `launch.json` to debug the fork using the executable created from compiling the tests without running