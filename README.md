#!/usr/bin/env sh

# 忽略错误
set -e

# 构建
pnpm run docs:build

# 进入待发布的目录
cd .vitepress/dist

git init
git add -A
git commit -m 'deploy'

# 如果发布到 https://<USERNAME>.github.io/<REPO>
git push -f git@github.com:huccct/huccct.github.io.git master


cd -
