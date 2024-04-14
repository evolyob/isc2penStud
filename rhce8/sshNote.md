```
ssh 不檢查指紋直接過去
ssh -o StrictHostKeyChecking=no <ip>

sftp = /usr/libexec/openssh/sftp-server


PermitRootLogin yes //允許使用root登入
PubkeyAuthentication yes  //表示支持公鑰認證
AuthorizedKeyFile .shh/authores_keys  //公要基於認證方式開始起後對放存放位址
PasswordAuthentication yes //支持密碼認證

/etc/ssh/sshd_config
改22 -->port 32222
port 32222

setenforce 0
systemctl stop firewalld
systemctl restart sshd

ssh -p 32222 -o StrictHostKeyChecking=no <ip>

PermitRootLogin no //不允許使用root登入


PubkeyAuthentication yes  //表示支持公鑰認證

ssh-keygen 在客戶端生成非對稱密鑰 /root/.ssh/id_rsa
AuthorizedKeyFile .shh/authores_keys  //公要基於認證方式開始起後對放存放位址
mkdir .ssh
touch authorized_keys

ssh-copy-id -p 32222 <name@ip>

ssh -i .ssh/id_dsa -p 32222 <name@ip>

遠端下命令
ssh -p 32222 <name@ip> "<command line>"

遠端複製文件
scp -P 32222 <file> <name@ip>:</path>
sftp -p 32222 <name@ip>

```
