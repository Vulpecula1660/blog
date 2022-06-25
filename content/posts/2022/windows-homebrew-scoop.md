---
title: "Windows 也有 Homebrew : Scoop"
date: 2022-06-25T13:49:19+08:00
tags: ["windows","scoop"]
categories: ["輕技術"]
---

## Homebrew
> Homebrew is the easiest and most flexible way to install the UNIX tools Apple didn’t include with macOS. It can also install software not packaged for your Linux distribution to your home directory without requiring sudo.

Homebrew 是在 macOS 上很好用的套件管理工具，可以輕易地在 command-line 安裝各種工具，但只有 macOS 可以使用，不過其實在 Windows 也有可以替代的工具，那就是 - Scoop

## [Scoop](https://scoop.sh/)
> A command-line installer for Windows

特點:
- 統一將所有程序安裝在 **~\scoop**
- 在安裝過程中不會跳出權限視窗
- 隱藏 GUI 介面安裝流程
- 防止安裝大量程序造成 PATH 污染
- 避免安裝和卸載程序的意外副作用
- 自動查找並安裝依賴項
- 自動執行所有額外的設置步驟以獲得工作程序

#### 如何安裝
開啟 5.1 版以上的 PowerShell terminal 並打入指令
```shell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser # Optional: Needed to run a remote script the first time
> irm get.scoop.sh | iex
```

#### 常用指令
```shell
# 尋找套件
> scoop search <package name>

# 安裝套件
> scoop install <package name>

# 移除套件
> scoop uninstall <package name>

# 更新所有已安裝的套件
> scoop update *
```

#### 使用心得
在使用 mac 時很習慣使用 Homebrew 來安裝與管理套件，因此在使用 Windows 時也希望找到類似的工具來使用，用了一陣子後覺得可以達到 Homebrew 的效果，因此也很推薦大家使用!

如果不確定你現在使用的套件是否能夠在 Scoop 上下載可以到他的[官網](https://scoop.sh)搜尋看看。

![scoop-search](/post/2022/scoop/scoop-search.png)

有時候他會顯示兩條指令，**bucket** 可以理解成儲存庫，如果你的電腦中缺少這個儲存庫便無法下載存放在那儲存庫的套件，因此要先下 **scoop bucket add** 的指令。