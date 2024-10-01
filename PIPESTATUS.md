`PIPESTATUS` is an [[array]] [[variable]] that holds the [[exit status]] of the last foreground [[pipeline]] command in [[bash]] scripting.
```bash
command1 | command2 | command3
echo ${PIPESTATUS[0]}  # Status of command1
echo ${PIPESTATUS[1]}  # Status of command2
echo ${PIPESTATUS[2]}  # Status of command3
```

#linux #cli