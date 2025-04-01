## IDE
正确的顺序是：本地 Mac → SSH 到远程服务器 → 在远程服务器上启动 TMUX → 在 TMUX 中运行命令。


```bash
conda init
source ~/.bashrc
conda activate azureml_py38_PT_and_TF
```



以下是你需要的命令顺序：

```
ssh -p 5054 scpdxcs@lab-a5d32e49-279a-45c0-8739-8b385433bea5.westeurope.cloudapp.azure.com
tmux new -s training
conda init
source ~/.bashrc
conda activate azureml_py38_PT_and_TF
```

在TMUX中常用快捷键：
- `Ctrl+b` 然后 `d` - 分离会话（保持运行）
- `tmux a -t training` - 重新连接到会话
- `Ctrl+b` 然后 `"` - 水平分割
- `Ctrl+b` 然后 `%` - 垂直分割
- `Ctrl+b` 然后方向键 - 在窗格间移动
- `Ctrl+b` 然后 `x` - 关闭当前窗格

`exit`会完全关闭窗格和可能的会话，如果你在运行训练脚本这类长时间任务，一定要使用 detach（Ctrl+b 然后 d）来保持任务在后台继续运行。


## Jupyter

用 VS Code 的 Remote SSH 插件和 Jupyter 插件是一个更现代、更简便的方法！这种方式确实可以替代文档中描述的手动 SSH 隧道设置。

## Git

install plugins in vscode
also, generate ssh and set up git

```
ssh-keygen -t ed25519 -C "jeremy@youngtalent.ai"
ssh-add ~/.ssh/id_ed25519
cat ~/.ssh/id_ed25519.pub
ssh -T git@github.com
git clone git@github.com:wgu9/cs234-hw.git
git config --global user.name "wgu9"
git config --global user.email "jeremy@youngtalent.ai"
```