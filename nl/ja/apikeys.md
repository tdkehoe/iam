---

copyright:

  years: 2015, 2017
lastupdated: "2017-08-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# API キーの管理
{: #manapikey}

アプリケーション・プログラミング・インターフェース・キー (API キー) は、呼び出し側プログラム、その開発者、またはそのユーザーを Web サイトが識別できるように、アプリケーション・プログラミング・インターフェース (API) を呼び出すコンピューター・プログラムによって渡されるコードです。API キーは、API の使用方法を追跡して制御するため (例えば、サービスのご利用条件に定義されているような、API の悪用または不正利用を防止するため) に使用されます。API キーは、多くの場合、認証のための固有 ID と秘密トークンの両方として機能し、通常はそのキーに関連付けられたユーザーに特定の一連のアクセス権限を持ちます。API キーは、各ユーザーに固有であることを保証するために、汎用固有 ID (UUID) システムに基づくことができます。

フェデレーテッド・ユーザーまたは非フェデレーテッド・ユーザーは、API キーを作成し、CLI で使用したり、ユーザー名としてログインするための自動化の一部として使用したりすることができます。キーのリスト、キーの作成、キーの更新、またはキーの削除を行うことにより、{{site.data.keyword.Bluemix_notm}} UI または {{site.data.keyword.Bluemix_notm}} CLI を使用して API キーを管理できます。{{site.data.keyword.Bluemix_notm}} API キーを UI で管理するには、**「管理」** &gt;**「セキュリティー」** &gt; **「Bluemix API キー」**に移動して、説明および日付と共に API キー・リストを表示します。次に、このページから API キーを作成、編集、および削除できます。使用可能な CLI コマンドの完全リストについては、[`bluemix iam api-keys`](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam) を参照してください。

[フェデレーテッド・ユーザー](/docs/admin/adminpublic.html#federatedid)の場合、`BLUEMIX_API_KEY` 環境変数を使用することにより、API キーを使用してログインすることができます。ログインのための API キーの使用について詳しくは、『[{{site.data.keyword.Bluemix_notm}} CLI `bluemix login` コマンド](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_login)』および『[cf CLI `cf login` コマンド](/docs/cli/reference/cfcommands/index.html#cf_login)』を参照してください。

## API キーの作成

{{site.data.keyword.Bluemix_notm}} ユーザーは、プログラムまたはスクリプトを使用可能にする際に、パスワードをスクリプトに配布せずに、API キーを使用できます。API キーを使用する利点は、ユーザーまたは組織が異なるプログラム用に複数の API キーを作成し、暗号漏えいが発生した場合、他の API キーやユーザーを妨害せずに、個別に API キーを削除できることです。

UI で API キーを作成するには、以下の手順を実行します。

1. **「管理」** &gt; **「セキュリティー」** &gt; **「Bluemix API キー」**に移動します。
2. **「API キーの作成」**をクリックします。
3. API キーの名前と説明を入力します。
4. **「API キーの作成」**をクリックします。
5. 次に、**「表示」**をクリックして API キーを表示し、後で使用するためにコピーして保存するか、または**「API キーのダウンロード」**をクリックします。

**注**: API キーは、作成時にのみ表示またはダウンロードできます。API キーが失われた場合は、新規 API キーを作成する必要があります。

CLI で API キーを作成するには、以下の手順を実行します。

1. コマンド・プロンプトに `bluemix iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]` と入力し、名前と説明、およびキーを保存するためのファイルを指定します。例えば次のようにします。

```
bluemix iam api-key-create MyKey -d "this is my API key" -f key_file
``` 

CLI を使用して API キーを作成した後は、以下に示すように、いくつかの方法でそのキーを bx CLI で使用できます。

* `bx login` コマンドを使用して入力する。
```
 bx login --apikey <your api key>
```
* API キー・ファイルを作成し、以下のように `bx login` コマンドで使用する。 
 ```
 bx login --apkey @apikeyfile
 ```
`apikeyfile` は、`bx iam api-key-create` コマンドで `—file` オプションを使用して作成されます。
* コマンド・プロンプトに `BLUEMIX_API_KEY=<your api key>` と入力し、次に `bx login` を入力することにより環境変数を設定できます。
* あるいは、bx CLI を避け、単に API キーを使用して cf CLI にログインする場合は、以下のように入力します。
 ```
 cf login -u apikey -p <yourapikey>
 ```
このオプションでは、ユーザー名 `apikey` を使用し、パスワードはご使用の`apikey` です。これで、Eclipse などの他のツールや、ユーザー名とパスワードのみを受け入れる `cf login` を予期している他の場所で `apikey` を使用できるようになりました。

## API キーの編集

API キーの名前や説明を変更する場合は、UI または CLI で以下の手順を実行します。

API キーを編集するには、以下の手順を実行します。

1. **「管理」** &gt; **「セキュリティー」** &gt; **「Bluemix API キー」**に移動します。
2. 表にリストされた API キーの**「アクション」**メニューで、**「名前および説明の編集 (Edit the name & description)」**をクリックします。 
3. API キーの情報を更新します。
4. **「API キーの更新」**をクリックします。

CLI を使用して API キーを編集するには、以下の手順を実行します。

1. コマンド・プロンプトに、キーの古い名前、新しい名前、および説明を指定して `bluemix iam api-key-update NAME [-n NAME] [-d DESCRIPTION]` と入力します。例えば次のようにします。

```
bluemix iam api-key-update MyCurrentName -n MyNewName -d "the new description of my key"
```

## API キーの削除

キーのローテーション戦略を使用している場合は、古いキーを削除し、新しいキーに置き換えることができます。

API キーを削除するには、以下の手順を実行します。 

1. **「管理」** &gt; **「セキュリティー」** &gt; **「Bluemix API キー」**に移動します。
2. 表にリストされた API キーの**「アクション」**メニューで、**「削除」**をクリックします。
3. 次に、**「キーの削除」**をクリックして、削除を確認します。

CLI を使用して API キーを削除するには、以下の手順を実行します。
1. コマンド・プロンプトに、削除するキーを指定して `bluemix iam api-key-delete NAME` と入力します。
