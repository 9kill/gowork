#解决github鉴权失败问题
 ➜  gowork git:(master) git push -u origin master
Username for 'https://github.com': 9kill
Password for 'https://9kill@github.com':
remote: Support for password authentication was removed on August 13, 2021. Please use a personal access token instead.
remote: Please see https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/ for more information.
fatal: 'https://github.com/9kill/gowork.git/' 鉴权失败

1.添加本地ssh的公钥
方法 github 帐户中缺少 SSH Keys

从~/.ssh目录复制本地公共 ssh 密钥

粘贴到 Github > Settings > SSH and GPG Keys > New SSH Key

试试ssh -T git@github.com 这应该输出

你好xxxxxx！您已成功通过身份验证，但 GitHub 不提供 shell 访问。

2.不要使用HTTPS git URL，使用下面命令改变现有的远程URL
git remote set-url origin git@github.com:xxxname/xxxproject.git
