# git 异常处理

## git "fatal:loose object"

### 1. 重新克隆

```bash
cp -R foo foo-bak #备份

git clone git@www.mydomain.de:foo foo-newclone
rm -rf foo/.git
mv foo-newclone/.git foo
rm -rf foo-newclone
```

### 2. relog

```bash
rm .git/objects/40/bda4e3b79c3d7bf598df31d9e68470f97a3f79(替换你出错的文件地址)
git fsck --full
git reflog
```

### 3. fetch

```bash
cp -R foo foo-backup
rm -fr .git
git init
git remote add origin [your-git-remote-url]
git fetch
git reset --mixed origin/master
git branch --set-upstream-to=origin/master master
```

## 脱离版本控制

git rm --cached path
