# 教室環境のセットアップ
## 1. DO180ラボ環境において利用可能なOpenShiftアカウント情報を確認します
## 2. workstationで /usr/local/etc/ocp4.config ファイルを作成します
ターミナルにおいて、sudo vi /usr/local/etc/ocp4.config を実行し、
コピーした内容をCtrl-vで貼り付け、ご自分のOpenShiftアカウントに合わせて編集します。

```
RHT_OCP4_MASTER_API=<Master API>
RHT_OCP4_WILDCARD_DOMAIN=<Wildcard Domain>
RHT_OCP4_DEV_USER=<OpenShift User>
RHT_OCP4_DEV_PASSWORD=<OpenShift Password>
```
注意：WILDCARD DOMAINは apps.<ドメイン名> になります。このドメイン名は、MASTER APIのapi.<ドメイン名>と同じです。

## 3. OpenShiftにログインできることを確認します
ターミナルで以下のコマンドを実行し、OpenShiftにログインできることを確認します。
```
$ source /usr/local/etc/ocp4.config
$ oc login -u ${RHT_OCP4_DEV_USER} -p ${RHT_OCP4_DEV_PASSWORD} ${RHT_OCP4_MASTER_API}
$ oc whoami
```
