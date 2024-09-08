# 清除git所有历史

为什么会需要这个呢？
```Shell
git checkout --orphan new-branch
git add -A
git commit -m "It's hurricane."
git branch -D main
git branch -m main
git push -f origin main
```