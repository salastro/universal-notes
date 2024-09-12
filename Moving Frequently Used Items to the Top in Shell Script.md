This is a common pattern in UI/UX design, where frequently used items are prioritized, minimizing the time required for future access.

```sh
sed -i "/$chosen/d" $file
echo $chosen | cat - $file > /tmp/file.txt && mv /tmp/file.txt /path/to/file.txt
```

- First, `sed` removes any previous occurrence of the selection from the file.
- Then, the chosen item is prepended to the file and written to a temporary file (`/tmp/emoji.txt`), which is moved back to the original file.