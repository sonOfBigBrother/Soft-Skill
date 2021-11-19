### 国内访问github报Timeout:443

参考这篇[掘金blog](https://juejin.cn/post/6844904193170341896)即可，已亲自验证过。

### 工程化配置commit规范

参考[该blog](https://juejin.cn/post/6844903710112350221)，并运用到实际项目中以加深印象——已经实际应用到具体项目中，验证该博客的正确性。

### 本地同步所有远程分支

```bash
# track all remote branches:
git branch -r | grep -v '\->' | while read remote; do git branch --track "${remote#origin/}" "$remote"; done
# update all local copies of remote branches
git fetch --all
# update all local tracking branches
git pull --all
```

#### 参考资料

【1】[SO上的解答](https://stackoverflow.com/questions/10312521/how-to-fetch-all-git-branches)

### 删除远程仓库除指定分支外的所有分支

删除除 master 外的所有远程分支

```bash
git branch -r | grep 'origin' | grep -v 'master$' | grep -v HEAD | cut -d/ -f2- | while read line; do git push origin :heads/$line; done;
```

#### 参考资料

【1】[SO](https://stackoverflow.com/questions/54808390/how-to-delete-all-git-remote-branches-except-master)

### 删除远程/本地仓库tags

```bash
#delete all the remote tags with the pattern your looking for, ie. DEV-
git tag | grep <pattern> | xargs -n 1 -i% git push origin :refs/tags/%
#delete all your local tags
git tag | xargs -n 1 -i% git tag -d %
#fetch the remote tags which still remain
git fetch
```

#### 参考资料

【1】[Github上的项目](https://gist.github.com/shsteimer/7257245)
