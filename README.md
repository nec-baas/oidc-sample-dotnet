oidc-sample-dotnet: OpenID Connect 認証サンプル（.NET アプリケーション）
=======================================================================
.NETアプリケーションでOpenID Connect 認証を行うためのサンプルです。

BaaS サーバ 事前準備
----------------------
先に BaaS サーバ上に OpenID Connect を設定したテナントを作成しておく必要があります。  
手順は以下の通りです。

1. BaaSコンソールでテナントを新規作成する。認証方式に 通常認証+OIDC認証 を指定すること。
2. OpenID Connect 設定画面の"OPリスト"から使用するOP種別の設定を行う。

アプリケーション 事前設定
-----------------------
OIDCAuthNativeAppTP/Top.xaml.cs 内の以下変数に
BaaSのAPIベースURL、テナントID、アプリID、アプリキー、OP種別などを設定してください。

### 設定対象
* EndpointUrl
* TenantId
* AppId
* AppKey
* OpType  
  設定可能な値は以下の通りです。  
    * google: Google
    * other: OpenAM
    * adfs: ADFS (Windows Server 2016)  
"adfs"を指定する場合は、以下Scopeを "openid profile email" としてください。
* Scope (オプション)

利用手順
--------
サンプルアプリケーションを起動し、以下のメニューを選択してください。

1. 認証開始  
システムデフォルトのブラウザを起動し、BaaSサーバへ認証開始要求を行います。  
OpenID Connect認証が成功するとコンソール画面にトークン情報を表示します。  
2. ログイン  
取得したトークン情報を用いてBaaSサーバへのログインを行います。  
認証未実施時は、ログインを行いません。  
ログイン成功時は、ログイン時に取得できるユーザ情報をコンソール画面に表示します。
