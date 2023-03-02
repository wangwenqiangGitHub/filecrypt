# filecrypt
## Summary

filecrypt - A simple tool to encrypt/decrypt files with user supplied password. Without the right password the files can't be decrypted.
## Usage
```c
usage: ./filecrypt [-e|-d] [-r] [-p password] [-a algorithm] [-h] [-t num_threads] [-D] path
  -e        encrypt the files in the path
  -d        decrypt the files in the path
  -r        recursive the path
  -p        password to encrypt or decrypt
  -a        select algorithm to encrypt and decrypt the files which encrypted by it
            supported algorithms: [xor, aes], xor is default
  -t        thread num to work, range: [1 - cpu_numbers], default: 1
  -D        open debug mode
  -n        no delete files which have been encrypted or decrypted
  -o        overwrite when the target file exists
  -h        show this usage
```
## File encrypt/decrypt algorithms
1. XOR
2. AES
3. ...

## Compile
Execute "make" in the root directory.
## Timeline
```c
2019-04-07  first commit
2019-04-13  add aes supported and fix the security issue
2019-12-08  add multi-thread
2020-01-01  fix integer overflow and crash when decrypting the big file
2021-08-24  encrypt the file name
2021-12-25  add the switch to overwrite the files and whether delete the origin files
```

# 文件加密解密使用

- 测试命令
```
#新建test.txt
./filecrypt -e -p <密码>(例如:test) -a <加密算法>(例如:aes) aa.txt
./filecrypt -d -p <密码>(test) -a <加密算法>(aes) <上一次加密生成的文件名字>167775885484724000
```
