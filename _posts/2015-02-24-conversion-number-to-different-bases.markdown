## Input Hexadecimal to output Decimal

```sh
echo "ibase=16; FFF" | bc
printf "%d" 0xfff
```

## Input Hexadecimal to output Octal

```sh
echo "ibase=16;obase=8; FFF" | bc
```
