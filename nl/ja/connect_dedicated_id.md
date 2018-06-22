---



copyright:

  years: 2015，2018

lastupdated: "2018-05-22"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# 専用 ID とパブリック IBM ID との接続
{: #connect_dedicated_id}

パブリック IAM サービスが使用可能な専用クラウドにログインするには、専用 ID ではなくパブリック IBM ID を使用して {{site.data.keyword.Bluemix_notm}} CLI にログインする必要があります。


```
  $ ibmcloud login -a https://api.{dedicated_env}.bluemix.net
  API endpoint: https://api.{dedicated_env}.bluemix.net

  Public IAM token service is available in the dedicated environment.
  Log in with your public IBMid, or use '--no-iam' to log in as a dedicated user only.

  Email>
```

専用 ID が既にパブリック IBM ID に接続されている場合は、認証が行われてログインします。

```
  Authenticating...
  OK

  Connected to dedicated user my_dedicated_id
```

しかし、専用 ID がパブリック IBM ID に接続されていない場合は、以下のように、パブリック IBM ID に手動で接続するよう求めるプロンプトが出されます。

```
  You are logging in with an IBMid that is not associated with any dedicated user.
  To set up the connection, input the credentials of the dedicated user.

  Choose a credential type:
  1. User name and password
  2. One Time Code (Get one at https://login.{dedicated_env}.bluemix.net.com/passcode)
  Enter a number>
```

専用 ID の資格情報を入力するオプションを選択します。 認証に成功すると、専用 ID はパブリック IBM ID に接続されます。

## ローカル UAA サーバーへのログインの強制

専用 ID での UAA サーバーへのログインを強制するには、`ibmcloud login` コマンドに `--no-iam` オプションを指定します。

```
  $ ibmcloud login --no-iam
```

## 専用 ID のパブリック IBM ID からの切断 

`ibmcloud iam dedicated-id-disconnect` を使用して、パブリック IBM ID と接続された専用 ID を切断できます。

```
  $ ibmcloud iam dedicated-id-disconnect
  Do you really want to disconnect my_dedicated_id from public IBMid? (Y/N)> y
  Disconnecting dedicated user my_dedicated_id from public IBMid...
  OK

  Logging out...
  OK
```
