# 文件逐行读取
```
    while IFS='' read -r line || [[ -n "$line" ]]; do
        echo "text read from file: $line"
    done < ${filename}
```
