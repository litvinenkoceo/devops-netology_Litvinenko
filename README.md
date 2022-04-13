# Задание 2.4 "Инструменты Git"

## 1. commit aefea      
> git show aefea

commit aefead2207ef7e2aa5dc81a34aedf0cad4c32545
Update CHANGELOG.md

## 2. коммит 85024d3     
> git show 85024

commit 85024d3100126de36331c6982bfaac02cdab9e76 (tag: v0.12.23)

## 3. b8d720 имеет 2 родителя:
> git show --pretty=format:' %P' b8d720

56cd7859e05c36c06b56d013b55a252d0bb7e158
9ea88f22fc6269854151c571162c5bcf958bee2b

## 4. v0.12.23..v0.12.24    
> git log v0.12.23..v0.12.24 --oneline

- 33ff1c03b v0.12.24
- b14b74c49 [Website] vmc provider links
- 3f235065b Update CHANGELOG.md
- 6ae64e247 registry: Fix panic when server is unreachable
- 5c619ca1b website: Remove links to the getting started guide's old location
- 06275647e Update CHANGELOG.md
- d5f9411f5 command: Fix bug when using terraform login on Windows
- 4b6d06cc5 Update CHANGELOG.md
- dd01a3507 Update CHANGELOG.md
- 225466bc3 Cleanup after v0.12.23 release

## 5. commint with func providerSource  
> git log -S'func providerSource' --oneline

8c928e835 main: Consult local directories as potential mirrors of providers

## 6. Все коммиты, в которых изменили функцию globalPluginDirs
> git grep 'func globalPluginDirs'
> git log -L :'func globalPluginDirs':plugins.go --oneline)

- 78b122055 - changed
- 52dbf9483 - changed
- 41ab0aef7 - changed
- 66ebff90c - changed
- 8364383c3 - created

## 7. Function synchronizedWriters author 
> git log -S'func synchronizedWriters(

commit 5ac311e2a91e381e2f52234668b49ba670aa0fe5
Author: Martin Atkins <mart@degeneration.co.uk>
Date:   Wed May 3 16:25:41 2017 -0700
 
