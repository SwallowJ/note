## vscode 远程连接

1. 生成密钥

```bash
ssh-keygen -t rsa #这里用-t指定加密算法
```

2. 发送密钥

```bash
$scp id_rsa.pub username@host:path
```

3. 放置密钥

```bash
#不存在authorized_keys
$mv id_rsa.pub ~/.ssh/authorized_keys

#存在authorized_keys
$cat id_rsa.pub >> ~/.ssh/authorized_keys
```

4. 修改文件权限
```
chmod 600 authorized_keys
```