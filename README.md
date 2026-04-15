# Tmux 快捷键速查表

---

## 目录

- [安装与配置](#安装与配置)
- [Tmux CLI 命令](#tmux-cli-命令)
- [复制模式](#复制模式)
- [窗格快捷键](#窗格快捷键)
- [窗口快捷键](#窗口快捷键)
- [会话快捷键](#会话快捷键)
- [命令模式](#命令模式)

---

## 安装与配置

```bash
apt update
apt install tmux

git clone https://github.com/MinsGoing/tmux.git
cp tmux/tmux.conf ~/.tmux.conf
tmux source-file ~/.tmux.conf
这一句后重新tmux source-file ~/.tmux.conf
sed -i 's/\r$//' ~/.tmux.conf # 若报错/root/.tmux.conf:2: unknown command: \r,则执行后重新source;否则无需执行,
```


## Tmux CLI 命令

### 新建会话

```bash
# 任选其一
tmux
tmux new
tmux new-session
```

命令模式写法：

```tmux
:new
```

新建一个名为 `myname` 的会话：

```bash
tmux new -s myname
```

```tmux
:new -s myname
```

查看所有会话：

```bash
tmux ls
tmux list-sessions
```

也可以使用快捷键：

```text
Ctrl+b s
```

### 附加到会话

附加到最近的会话：

```bash
tmux a
tmux at
tmux attach
tmux attach-session
```

附加到名为 `myname` 的会话：

```bash
tmux a -t myname
tmux at -t myname
tmux attach -t myname
tmux attach-session -t myname
```

### 结束会话

按名称结束会话：

```bash
tmux kill-ses -t myname
tmux kill-session -t myname
```

结束除当前会话外的所有会话：

```bash
tmux kill-ses -a
```

结束除 `myname` 外的所有会话：

```bash
tmux kill-ses -a -t myname
```

### 帮助与配置

查看 tmux 信息：

```bash
tmux info
```

重新加载配置：

```bash
tmux source-file ~/.tmux.conf
```

显示全局配置项：

```bash
tmux show-options -g
```

---

## 复制模式

| 快捷键 | 中文说明 |
|---|---|
| `Ctrl+b [` | 进入复制模式 |
| `Space` | 开始选择内容 |
| `Enter` | 复制已选内容 |
| `q` | 退出复制模式 |
| `Ctrl+b ]` | 粘贴 `buffer_0` 中的内容 |

---

## 窗格快捷键

| 快捷键 | 中文说明 |
|---|---|
| `Ctrl+b "` | 水平分割窗格 |
| `Ctrl+b %` | 垂直分割窗格 |
| `Ctrl+b !` | 将当前窗格拆分为独立窗口 |
| `Ctrl+b x` | 关闭当前窗格 |
| `Ctrl+b` + 方向键 | 在窗格之间移动 |
| `Ctrl+b Space` | 切换窗格布局 |
| `Ctrl+b {` | 向左移动当前窗格 |
| `Ctrl+b }` | 向右移动当前窗格 |
| `Ctrl+b o` | 切换到下一个窗格 |
| `Ctrl+b z` | 当前窗格全屏 / 取消全屏 |
| `Ctrl+b ;` | 切换到上一个活动窗格 |
| `Ctrl+b q` | 显示窗格编号 |
| `Ctrl+b q 0...9` | 跳转到指定编号的窗格 |

---

## 窗口快捷键

| 快捷键 | 中文说明 |
|---|---|
| `Ctrl+b c` | 新建窗口 |
| `Ctrl+b p` | 切换到上一个窗口 |
| `Ctrl+b n` | 切换到下一个窗口 |
| `Ctrl+b w` | 列出所有窗口 |
| `Ctrl+b ,` | 重命名当前窗口 |
| `Ctrl+b f` | 查找窗口 |
| `Ctrl+b l` | 切换到上一个活动窗口 |
| `Ctrl+b .` | 移动当前窗口 |
| `Ctrl+b &` | 关闭当前窗口 |
| `Ctrl+b 0...9` | 跳转到指定编号的窗口 |

> 备注：原网页在窗口部分也重复列出了分割窗格命令，这里已去重整理。

---

## 会话快捷键

| 快捷键 | 中文说明 |
|---|---|
| `Ctrl+b d` | 从当前会话分离 |
| `Ctrl+b s` | 显示所有会话 |
| `Ctrl+b $` | 重命名当前会话 |
| `Ctrl+b (` | 切换到上一个会话 |
| `Ctrl+b )` | 切换到下一个会话 |

---

## 命令模式

进入命令模式：

| 快捷键 | 中文说明 |
|---|---|
| `Ctrl+b :` | 打开命令输入模式 |

### 调整窗格大小

| 命令 | 中文说明 |
|---|---|
| `resize-pane -D 20` | 向下扩展 20 行 |
| `resize-pane -U 20` | 向上扩展 20 行 |
| `resize-pane -L 20` | 向左扩展 20 列 |
| `resize-pane -R 20` | 向右扩展 20 列 |

### 列表命令

| 命令 | 中文说明 |
|---|---|
| `list-keys` | 列出所有快捷键 |
| `list-panes` | 列出所有窗格 |
| `list-windows` | 列出所有窗口 |

### 缓冲区 / 复制相关

| 命令 | 中文说明 |
|---|---|
| `list-buffers` | 列出所有缓冲区 |
| `show-buffer` | 显示编号 `#0` 的缓冲区内容 |
| `capture-pane` | 捕获当前窗格内容到缓冲区 |
| `choose-buffer` | 显示并选择缓冲区进行粘贴 |
| `save-buffer a.txt` | 将缓冲区内容保存到文件 |
| `delete-buffer -b 1` | 删除编号为 1 的缓冲区 |

### 环境设置

| 命令 | 中文说明 |
|---|---|
| `set -g OPTION` | 为所有会话设置选项 |
| `setw -g OPTION` | 为所有窗口设置选项 |
| `setw -g mode-keys vi` | 启用 vi 风格按键 |
| `set -g prefix C-a` | 将前缀键设置为 `Ctrl+a` |

### 其他常用命令

| 命令 | 中文说明 |
|---|---|
| `swap-pane -s 3 -t 1` | 交换两个窗格 |
| `swap-window -t -1` | 将当前窗口向左移动 |
| `setw synchronize-panes` | 开启/设置窗格同步输入 |
| `join-pane -t :#` | 将窗格合并到目标位置 |

---

## 参考来源

- 原始页面：<https://banlyai.com/cheatsheet/docs/tmux.html>
