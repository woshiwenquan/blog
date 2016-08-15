layout: layout
title: Symfony2常见命令
date: 2016-08-15 22:09:07
tags:
---
## Symfony2 常用命令
### 删除缓存

```
$ php app/console cache:clear -e dev(prod)
```
### 从Bundle中生成Entity
```
$ php app/console doctrine:generate:entities ModelBunle
```
### 更新表
```
$  php app/console doctrine:schema:update --force
```
### 更新依赖的vender
```
$ composer update
```
### 根据src里的内容更新
```
$ php app/console assets:install
```
### 创建一个新的bundle
```
$ php app/console  generate:bundle
```
### 注意
symfony 3.0版本及以上，console在bin目录下
```
$ php bin/console 命令
```
