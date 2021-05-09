## 初回 vagrant up 後に必要な作業

### 共通
- ssh 鍵の作成
```
ssh-keygen -t rsa -b 4096 -C "$HOSTNAME" -f "$HOME/.ssh/id_rsa" -P "" && cat ~/.ssh/id_rsa.pub
```
- 公開鍵を github へ登録
- Windowsの公開鍵で vagrant で立てた環境にsshできるように `~/.ssh/authorized_keys` に Windows の公開鍵を登録

### Ansible ノードにする予定のマシン
- Ansible のホストマシンにする予定のマシンの公開鍵を `~/.ssh/authorized_keys` に登録

### Ansible のホストマシンにする予定のマシン
- zsh 入れたりいろいろ
- Ansible の install
  - https://docs.ansible.com/ansible/2.9_ja/installation_guide/intro_installation.html#ubuntu-ansible
- https://github.com/mirko-san/dev-env/tree/dev リポジトリの clone
- `ansible` ディレクトリで `ansible-playbook -i hosts.yml site.yml`

### vagrant で複数マシンを構築するときに嵌ったのでメモ
```
ip a
```
でIPアドレスの設定の確認ができる

#### Link
https://kazuhira-r.hatenablog.com/entry/2020/04/11/222841

## Link

### Ansible
https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html
https://github.com/ansible/ansible-examples/tree/master/lamp_simple


## TODO
- vagrant の provision で ansible 実行
  - https://qiita.com/ringo0321/items/38743442a9abfc3be5b2
