# このプロジェクト（リポジトリ）について
このリポジトリは Crisp Code が管理するサーバの構成を管理するためのAnsible playbookです。

## プレイブックの書き方
AnsibleにはRolesという記述するためのガイドラインのようなものがあります。
このリポジトリはできるだけ、Ansible Rolesの書き方に合わせています。
絶対ではないですが、できるだけこのルールに従った書き方をしていきましょう。

参考URL Ansible Roles
- http://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse_roles.html
- https://dev.classmethod.jp/server-side/ansible/introduction_about_role/

## ディレクトリ構造

```
├── group_vars   //ansible-playbook内で使用する全体的な変数を定義しています
├── host_vars    //各ホストごとの設定ファイル（IPアドレスやホスト名など）が書かれてたファイルがあります
└── roles
    ├── common    //すべてのサーバに設定するべき内容を記載しています 
    │   ├── files
    │   ├── handlers
    │   ├── tasks
    │   └── templates
    └── mysql     
        ├── files
        ├── handlers
        ├── tasks
        └── templates

```

common はすべてのサーバに適用されます。object,request,webなどの各ディレクトリは各ホストの設定が入っています。
handlers,task templateなどの使い分けはansible 公式を見てください。
