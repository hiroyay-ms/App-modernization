![Microsoft Cloud Workshop](images/ms-cloud-workshop.png)

App modernization  
Hands-on lab step-by-step  
March 2020

<br />

**Contents**

- [App modernization hands-on lab step-by-step](#app-modernization-hands-on-lab-step-by-step)
  - [要約および学習目標](#要約および学習目標)
  - [概要](#概要)
  - [ソリューション アーキテクチャ](#ソリューション-アーキテクチャ)
  - [要件](#要件)
  - [Exercise 1: 環境のセットアップ](#exercise-1-環境のセットアップ)
      - [Task 1: リソース グループの作成](#task-1-リソース-グループの作成)
      - [Task 2: リソース グループへのアクセス権限の付与](#task-2-リソース-グループへのアクセス権限の付与)
      - [Task 3: ストレージ アカウントの作成](#task-3-ストレージ-アカウントの作成)
      - [Task 4: SQL Server 2008 R2 仮想マシンの作成](#task-4-sql-server-2008-r2-仮想マシンの作成)
      - [Task 5: Azure SQL Database のプロビジョニング](#task-5-azure-sql-database-のプロビジョニング)
      - [Task 6: Azure Database Migration Service の作成](#task-6-azure-database-migration-service-の作成)
      - [Task 7: API App のプロビジョニング](#task-7-api-app-のプロビジョニング)
      - [Task 8: Azure Functions のプロビジョニング](#task-8-azure-functions-のプロビジョニング)
      - [Task 9: Cognitive Search Service のプロビジョニング](#task-9-cognitive-search-service-のプロビジョニング)
      - [Task 10: Cognitive Service アカウントの作成](#task-10-cognitive-service-アカウントの作成)
      - [Task 11: Azure Key Vault の作成](#task-11-azure-key-vault-の作成)
      - [Task 12: API Management のプロビジョニング](#task-12-api-management-のプロビジョニング)
      - [Task 13: SQL Server データベースの復元](#task-12-sql-server-データベースの復元)
      - [Task 14: Data Migration Assistant のインストール](#task-13-data-migration-assistant-のインストール)
  - [Exercise 2: Azure SQL Database へのオンプレミス データベースの移行](#exercise-2-azure-sql-database-へのオンプレミス-データベースの移行)
    - [Task 1: ContosoInsurance の構成](#task-1-contosoinsurance-の構成)
    - [Task 2: Azure SQL Database への移行の評価の実行](#task-2-azure-sql-database-への移行の評価の実行)
    - [Task 3: Data Migration Assistant を使用したデータベース スキーマの移行](#task-3-data-migration-assistant-を使用したデータベース-スキーマの移行)
    - [Task 4: SQL Server 2008 R2 仮想マシンの IP アドレスの取得](#task-4-sql-server-2008-r2-仮想マシンの-ip-アドレスの取得)
    - [Task 5: Azure Database Migration Service を使用したデータベースの移行](#task-5-azure-database-migration-service-を使用したデータベースの移行)
  - [Exercise 3: データベースのアップグレード後のセキュリティ強化](#exercise-3-データベースのアップグレード後のセキュリティ強化)
    - [Task 1: データの検出と分類の構成](#task-3-データの検出と分類の構成)
    - [Task 2: Advanced Data Security の脆弱性評価のレビュー](#task-2-advanced-data-security-の脆弱性評価のレビュー)
    - [Task 3: 動的データ マスクの有効化](#task-3-動的データ-マスクの有効化)
  - [Exercise 4: Key Vault の構成](#exercise-4-key-vault-の構成)
    - [Task 1: Key Vault アクセス ポリシーの追加](#task-1-key-vault-アクセス-ポリシーの追加)
    - [Task 2: SQL 接続文字列を格納する新しいシークレットの作成](#task-2-sql-接続文字列を格納する新しいシークレットの作成)
    - [Task 3: サービス プリンシパルの作成](#task-3-サービス-プリンシパルの作成)
    - [Task 4: Key Vault へのサービス プリンシパル アクセスの割り当て](#task-4-key-vault-へのサービス-プリンシパル-アクセスの割り当て)
  - [Exercise 5: Azure App Services への Web API の展開](#exercise-5-azure-app-services-への-web-api-の展開)
    - [Task 1: Visual Studio でソリューションを開く](#task-1-visual-studio--ソリューションを開く)
    - [Task 2: Key Vault を使用するための Web API の更新](#task-2-key-vault-を使用するための-web-wpi-の更新)
    - [Task 3: Azure 内の API App への Key Vault 構成セクションのコピー](#task-3-azure-内の-api-app-への-key-vault-構成セクションのコピー)
    - [Task 4: Azure への API の展開](#task-4-azure-への-api-の展開)
  - [Exercise 6: Azure App Services への Web アプリケーションの展開](#exercise-6-azure-app-services-への-web-アプリケーションの展開)
    - [Task 1: Web App のアプリケーション設定への API App URL の追加](#task-1-web-app-のアプリケーション設定への-api-app-url-の追加)
    - [Task 2: Azure への Web アプリケーションの展開](#task-2-azure-への-web-アプリケーションの展開)
  - [Exercise 7: Blob ストレージへの保険契約ドキュメントのアップロード](#exercise-7-blob-ストレージへの保険契約ドキュメントのアップロード)
    - [Task 1: PDF ファイルを格納するコンテナーの作成](#task-1-pdf-ファイルを格納するコンテナーの作成)
    - [Task 2: SAS トークンの作成](#task-2-sas-トークンの作成)
    - [Task 3: AzCopy を使用した Blob ストレージへの PDF の一括アップロード](#task-3-azcopy-を使用した-blob-ストレージへの-pdfの一括アップロード)
  - [Exercise 8: PDF にアクセスするための Azure Functions の作成](#exercise-8-pdf-にアクセスするための-azure-functions-の作成)
    - [Task 1:  Azure Functions へのアプリケーション設定の追加](#task-1-azure-functions-へのアプリケーション設定の追加)
    - [Task 2: プロジェクト環境変数の追加](#task-2-プロジェクト環境変数の追加)
    - [Task 3: Visual Studio での Azure Functions の作成](#task-3-visual-studio-での-azure-functions-の作成)
    - [Task 4: ローカル環境での関数のテスト](#task-4-ローカル環境での関数のテスト)
    - [Task 5: Azure Functions への関数の展開](#task-5-azure-functions-への関数の展開)
    - [Task 6: Azure Functions での Application Insights の有効化](#task-6-azure-functions-での-application-insights-の有効化)
    - [Task 7: Web Apps のアプリケーション設定への Azure Functions URL の追加](#task-7-web-apps-のアプリケーション設定への-azure-functions-url-の追加)
    - [Task 8: Web アプリからドキュメント取得のテスト](#task-8-web-アプリからドキュメント取得のテスト)
    - [Task 9: ライブ メトリックス ストリームの表示](#ライブ-メトリックス-ストリームの表示)
  - [Exercise 9: 保険契約ドキュメントへのフルテキスト検索機能の追加](#exercise-9-保険契約ドキュメントへのフルテキスト検索機能の追加)
    - [Task 1: ストレージ アカウントへの Azure Cognitive Search の追加](#task-1-ストレージ-アカウントへの-azure-cognitive-search-の追加)
    - [Task 2: 検索結果のレビュー](#task-2-検索結果のレビュー)
  - [Exercise 10: API Management への API のインポートと公開](#exercise-10-api-management-への-api-のインポートと公開)
    - [Task 1: API App のインポート](#task-1-api-app-のインポート)
    - [Task 2: Azure Functions のインポート](#task-2-azure-functions-のインポート)
    - [Task 3: 開発者ポータルからの API キーの取得](#task-3-開発者ポータルからの-api-キーの取得)
    - [Task 4: API Management エンドポイントを使用するための Web App の更新](#task-4-api-management-エンドポイントを使用するための-web-app-の更新)
  - [Exercise 11: PowerApps でのアプリの作成](#exercise-11-powerapps-でのアプリの作成)
    - [Task 1: PowerApps アカウントへのサインアップ](#task-1-powerapps-アカウントへのサインアップ)
    - [Task 2: 新しい SQL 接続の作成](#task-2-新しい-sql-接続の作成)
    - [Task 3: 新しいアプリの作成](#task-3-新しいアプリの作成)
    - [Task 4: アプリの設計](#task-4-アプリの設計)
    - [Task 5: アプリ設定の編集とアプリの実行](#task-5-アプリ設定の編集とアプリの実行)
  - [ワークショップ後の作業](#ワークショップ後の作業)
    - [Task 1: リソース グループの削除](#task-1-リソース-グループの削除)
    - [Task 2: Contoso-apps サービス プリンシパルの削除](#task-2-contoso-apps-サービス-プリンシパルの削除)

# **App modernization hands-on lab step-by-step**

## **要約および学習目標**
このハンズオン ラボでは、データベースのアップグレードと Azure への移行やサーバーレスおよびクラウド サービスの活用を目的としたアプリケーションの更新など、レガシ オンプレミス アプリケーションを最新化する手順を実装します。
このハンズオン ラボは、クラウド サービスを使用してレガシ オンプレミス アプリケーションおよびインフラストラクチャを最新化するためのソリューションを構築する能力の向上を目的としています。

## **概要**
Contoso, Ltd. (Contoso) は古くから存在する業界に新規参入した企業です。ニュージーランドのオークランドで 2011 年に設立された Contoso は、十分な保険に入っていない個人を対象としたニッチな市場で広範な長期保険サービスを提供しています。当初の予想よりも早いペースで成長を続けた Contoso では、その成長のスピードに対応することが困難になりつつありました。創業直後の 1 年間だけでも、同社のサービスに対する需要に応えるために 100 人以上の従業員を新規に雇用しました。Contoso は、保険契約と関連ドキュメントを管理するためにカスタム開発された PolicyConnect という Windows Forms アプリケーションを使用しています。PolicyConnect はオンプレミスの SQL Server 2008 R2 データベースをデータストアとして使用し、契約ドキュメントの格納には LAN 上のファイル サーバーが使用されています。契約の管理を目的としたこのアプリケーションとプロセスに対する負荷は限界に近づいています。
最近、Contoso は、契約者、仲買人、および従業員が Contoso ネットワークへの VPN 接続なしで契約情報にアクセスできる新しい Web およびモバイル プロジェクトを開始しました。Web プロジェクトは、REST API を使用して PolicyConnect データベースにアクセスする新しい .NET Core 2.2 MVC Web アプリケーションです。Contoso は、モバイル アプリや WinForms バージョンの PolicyConnect を始めとするすべてのアプリケーションで REST API を共有することを計画しています。現在は、オンプレミスで実行するプロトタイプの Web アプリケーションが存在し、Contoso では、このアプリをクラウドでホストすることが検討されています。しかし、Contoso にはクラウドの経験がないので、クラウドのすべてのマネージド サービスのメリットを活用する方法が不明です。同社は、現在までに作成されたアプリをクラウド ネイティブ アプリケーションに変換する方法を模索しています。
モバイル アプリの開発はまだ開始されていません。Contoso は、.NET 開発者が Android および iOS 上に PolicyConnect を実装するための容易なアプローチを探しています。
Contoso のアプリケーションをクラウドでホストするための準備の一環として、同社では、既存の SQL Server データベースを Azure 内の PaaS SQL サービスに移行することが計画されています。Contoso は、Azure の完全なマネージド SQL サービスで提供される高度なセキュリティ機能を活用したいと考えています。クラウドに移行することにより、社内の技術的能力が向上し、クラウドの強化機能やサービスを活用できるようになることが期待されています。Contoso が追加したいと考えている新しい機能は、仲買人からのドキュメントの自動転送、仲買人向けのセキュアなアクセス、契約情報へのアクセス、および分散する従業員が利用できる信頼性の高い契約情報の抽出です。PolicyConnect WinForms アプリケーションを使用する方針は確定していますが、クラウド ベースの API およびサービスを使用するためにアプリケーションを更新することが検討されています。さらに、Web およびモバイル アプリから取得できるように契約ドキュメントをクラウド ストレージに格納することも検討されています。

## **ソリューション アーキテクチャ**
![Solution Architecture](images/solution-architecture.png)
最初の手順は、**Azure Database Migration Service (DMS)** を使用して Contoso の SQL Server 2008 R2 データベースを **Azure SQL Database** に移行することです。Contoso では **Data Migration Assistant (DMA)** を使用して、Azure の完全なマネージド SQL データベース サービスに移行できることが確認されています。この評価では、Azure SQL Database の使用に関連する互換性の問題やサポートされていない機能は検出されませんでした。次に、Web および API アプリを **Azure App Services** に展開します。また、PolicyConnect へのリモート アクセスを提供するために、Xamarin を使用して Android および iOS 向けに構築されたモバイル アプリを作成します。Web App でホストされる Web サイトはブラウザー ベースのクライアント用のユーザー インターフェイスを提供し、Xamarin.Forms ベースのアプリが モバイル デバイス用の UI を提供します。モバイル アプリと Web サイトは両方とも、**API Management** の背後に配置された **Azure Functions** でホストされる Web サービスに依存します。レガシ Windows Forms デスクトップ アプリケーションの API をホストするために **API App** も展開します。**Blob Storage** に格納されたデータベースおよび契約ドキュメントへのアクセスを提供するために Azure Functions および Azure Functions プロキシによって軽量のサーバーレス API が提供されます。
API Management は、開発チームとアフィリエイト パートナー向けの API ストアを作成するために使用します。接続文字列などの機密構成データは **Key Vault** に格納され、必要な時に API または Web アプリからアクセスされるので、これらの設定がファイル システムに保存されることはありません。API App は、**Azure Cache for Redis** を使用してキャッシュ アサイド パターンを実装します。Blob Storage 内の契約ドキュメントにインデックスを作成するためにフルテキスト 検索を使用します。**Azure Search** のコグニティブ スキルを使用して検索インデックス エンリッチメントを有効にするために **Cognitive Services** を使用します。承認されたビジネス ユーザーにモバイル アプリおよび Web CRUD (create、read、update、delete) アプリケーションの作成を許可するために **PowerApps** を使用します。これらのアプリは、SQL Database および Azure Storage と対話します。**Microsoft Flow** によってモバイル通知を送信するための Office 365 電子メールおよびサービスとのオーケストレーションが実現します。これらのオーケストレーションは、PowerApps から独立して使用することに加えて、PowerApps から起動して追加ロジックを提供することができます。このソリューションでは、Azure AD で維持されているユーザーおよびアプリケーション ID を使用します。
>メモ: ここで紹介するソリューションは、考えられるさまざまなアプローチの中の 1 つです。

## **要件**
- Microsoft Azure サブスクリプション
  - 無料アカウントでは、このワークショップを実行することはできません
- Azure Active Directory テナント内での権限
   - Azure Active Directory アプリケーションおよびサービス プリンシパルの作成
   - サブスクリプションでの役割の割り当て
   - リソース プロバイダーの登録

## **Exercise 1: 環境のセットアップ**

### **Task 1**: リソース グループの作成

### **Task 2**: リソース グループへのアクセス権限の付与

### **Task 3**: ストレージ アカウントの作成

### **Task 4**: SQL Server 2008 R2 仮想マシンの作成

### **Task 5**: Azure SQL Database のプロビジョニング
このタスクでは、Azure SQL Database (Azure SQL DB) を展開します。
  1. [Azure Portal](https://portal.azure.com/) で**ポータルメニューの表示**を選択し、メニューから**リソースの作成**を選択
  2. Azure Market Place の検索ウィンドウに "sql database" と入力しエンターを押し、その検索結果から **SQL Database**を選択し**作成**を選択
  3. SQL データベースの作成の**基本**タブで以下を入力
     - プロジェクトの詳細
       - **サブスクリプション** : ハンズオンラボでで使用するサブスクリプションを選択
       - **リソースグループ** : 既存のリソースグループのリストから "hands-on-lab-SUFFIX" リソースグループを選択
     - データベースの詳細
       - **データベース名** : "contosoInsurance" と入力
       - **サーバー** : **新規作成**を選択し、新しいサーバーのブレードで以下を入力
         - **サーバー名** : "contosoinsuranceSUFFIX" と入力
         - **サーバー管理者ログイン** : "demouser" と入力
         - **パスワード** : "Password.1!!" と入力
         - **場所** : ハンズオンラボで使用するリソースのリージョンを選択
         - **Azure サービスにサーバーへのアクセスを許可する** : チェックボックスをオン
         - **OK** を選択
       - **SQL エラスティック プールを使用しますか?** : いいえ を選択
       - **コンピューティングとストレージ** : デフォルトで選択されている 汎用目的, Gen5, 2 仮想コア, 32 GB ストレージのままで OK ( もし、これと異なるものが選択されている場合、\[ データベースの構成 ] から選択し直してください ) 
  4. **次: ネットワーク**を選択
  5. 選択されている接続方法が**アクセスなし**となっていることを確認
  6. **次: 追加設定**を選択
  7. **追加設定**タブで**Advanced Data Security**の**無料試用版の開始**を選択
  8. **確認および作成**を選択
  9. **確認および作成**タブで**作成**を選択し SQL Database を展開

### **Task 6**: Azure Database Migration Service の作成
このタスクでは、Azure Database Migration Service (DMS) のインスタンスを展開します。
  1. [Azure Portal](https://portal.azure.com/) で**ポータルメニューの表示**を選択し、メニューから**リソースの作成**を選択
  2. Azure Market Place の検索ウィンドウに "database migration" と入力しエンターを押し、その検索結果から **Azure Database Migration サービス**を選択し**作成**を選択
  3. 移行サービスの作成の**基本**タブで以下を入力
     > Note: `あなたのサブスクリプションは Microsoft.DataMigration への適切なアクセスを持っていません`というメッセージが表示された場合、次に進む前にブラウザウィンドウをリフレッシュ ( 再読み込み ) してください。もしメッセージが引き続き表示される場合、リソースプロバイダーが正常に登録されていることを確認してください。正常に登録されている場合、このメッセージを無視しても大丈夫です。
     - プロジェクトの詳細
       - **サブスクリプション** : ハンズオンラボでで使用するサブスクリプションを選択
       - **リソースグループ** : 既存のリソースグループのリストから "hands-on-lab-SUFFIX" リソースグループを選択
     - インスタンスの詳細
       - **移行サービス名** : "contoso-dms-SUFFIX" と入力
       - **場所** : ハンズオンラボで使用するリソースのリージョンを選択
       - **サービスモード** : Azure を選択
       - **価格レベル** : \[ レベルの構成 ] を選択し、遷移した画面で Premium: 4 vCores を選択し \[ 適用 ] を選択
  4. **次: ネットワーク**を選択
  5. **ネットワーク**タブにおいて既存の仮想ネットワークのリストから **hands-on-lab-SUFFIX-vnet/default** の横にあるチェックボックスを選択します。これにより、DMS インスタンスは LabVM や SqlServer2008 仮想マシンと同じ VNet に展開されます。
  6. **確認および作成**を選択
  7. **作成**を選択
  8. Azure Data Migration Service の展開には 15 分程かかります。この待ち時間の間に次のタスクに進むことができます。

### **Task 7**: Web App のプロビジョニング
このタスクでは、Contoso Insurance の Web アプリケーションの実行環境を提供する App Service (Web App) を展開します。
  1. [Azure Portal](https://portal.azure.com/) で**ポータルメニューの表示**を選択し、メニューから**リソースの作成**を選択
  2. Azure Market Place の検索ウィンドウに "web app" と入力しエンターを押し、その検索結果から **Web アプリ**を選択
  3. Web アプリのブレードから**作成**を選択
  4. Web アプリの作成の**基本**タブで以下を入力
     - プロジェクトの詳細
       - **サブスクリプション** : ハンズオンラボでで使用するサブスクリプションを選択
       - **リソースグループ** : 既存のリソースグループのリストから "hands-on-lab-SUFFIX" リソースグループを選択
     - インスタンスの詳細
       - **名前** : "contoso-web-SUFFIX" と入力
       - **公開** : コード を選択
       - **ランタイムスタック** : .NET Core 3.0 を選択
       - **オペレーティングシステム** : Windows を選択
       - **地域** : ハンズオンラボで使用するリソースのリージョンを選択
     - App Service プラン
       - **プラン** : **新規作成**を選択し名前に**hands-on-lab-asp**を入力
       - **SKU とサイズ** : デフォルトで選択されている Standard S1 のままで OK ( もし、これと異なるものが選択されている場合、\[ サイズを変更します ] から選択し直してください ) 
  5. **次: 監視**を選択
  6. **監視**タブにおいて Application Insights を有効にするで**いいえ**を選択
  7. **確認および作成**を選択
  8. **作成**を選択
  9. Web App の展開には数分かかります。この待ち時間の間に次のタスクに進むことができます。

### **Task 8**: API App のプロビジョニング

### **Task 9**: Azure Functions のプロビジョニング
このタスクでは、Azure BLOB ストレージから PDF ドキュメントを取得するために使用する Function App を展開します。
  1. [Azure Portal](https://portal.azure.com/) で**ポータルメニューの表示**を選択し、メニューから**リソースの作成**を選択
  2. Azure Market Place の検索ウィンドウに "function app" と入力しエンターを押し、その検索結果から **関数アプリ**を選択
  3. 関数アプリのブレードから**作成**を選択
  4. 関数アプリの作成の**基本**タブで以下を入力
     - プロジェクトの詳細
       - **サブスクリプション** : ハンズオンラボでで使用するサブスクリプションを選択
       - **リソースグループ** : 既存のリソースグループのリストから "hands-on-lab-SUFFIX" リソースグループを選択
     - インスタンスの詳細
       - **関数アプリ名** : "contoso-func-SUFFIX" と入力
       - **公開** : コード を選択
       - **ランタイムスタック** : .NET Core を選択
       - **バージョン** : 3.1 を選択
       - **地域** : ハンズオンラボで使用するリソースのリージョンを選択
  5. **ホスト中**を選択
    - **ストレージアカウント** : Task 3 で作成したストレージアカウントを選択
    - **オペレーティングシステム** : Windows を選択
    - **プランの種類** : 消費量 ( サーバーレス )　を選択
  6. **次: 監視**を選択
    - **Application Insights を有効にする** : **いいえ** を選択
  7. **確認および作成**を選択
  8. **作成**を選択 

### **Task 10**: Cognitive Search Service のプロビジョニング
このタスクでは、Azure Cognitive Search Service を展開します。
  1. [Azure Portal](https://portal.azure.com/) で**ポータルメニューの表示**を選択し、メニューから**リソースの作成**を選択
  2. Azure Market Place の検索ウィンドウに "Azure Cognitive Search" と入力しエンターを押し、その検索結果から **Azure Cognitive Search**を選択
  3. Azure Cognitive Search のブレードから**作成**を選択
  4. 新しい検索サービスの作成の**基本**タブで以下を入力
     - プロジェクトの詳細
       - **サブスクリプション** : ハンズオンラボでで使用するサブスクリプションを選択
       - **リソースグループ** : 既存のリソースグループのリストから "hands-on-lab-SUFFIX" リソースグループを選択
     - インスタンスの詳細
       - **URL** : "contoso-search-SUFFIX" と入力
       - **場所** : ハンズオンラボで使用するリソースのリージョンを選択
       - **価格レベル** : デフォルトで選択されている Standard のままで OK ( もし、これと異なるものが選択されている場合、\[ 価格レベルの変更 ] から選択し直してください )
  5. **確認および作成**を選択
  6. **作成**を選択
  7. Azure Cognitive Search Service の展開には 10 分程かかります。この待ち時間の間に次のタスクに進むことができます。
  
### **Task 11**: Cognitive Service アカウントの作成
このタスクでは、Azure Cognitive Search Account を展開します。
  1. [Azure Portal](https://portal.azure.com/) で**ポータルメニューの表示**を選択し、メニューから**リソースの作成**を選択
  2. Azure Market Place の検索ウィンドウに "cognitive services" と入力しエンターを押し、その検索結果から **Cognitive Services**を選択
  3. Cognitive Service のブレードから**作成**を選択
  4. 新しい検索サービスの作成の**基本**タブで以下を入力
     - **名前** : "ontoso-cog-services" と入力
     - **サブスクリプション** : ハンズオンラボでで使用するサブスクリプションを選択
     - **場所** : ハンズオンラボで使用するリソースのリージョンを選択
     - **価格レベル** : S0 を選択
     - **リソースグループ** : 既存のリソースグループのリストから "hands-on-lab-SUFFIX" リソ      - 注意事項を確認しチェックボックスにチェック
  . **作成**を選択

### **Task 12**: Azure Key Vault の作成

### **Task 13**: API Management のプロビジョニング

### **Task 14**: SQL Server データベースの復元

### **Task 15**: Data Migration Assistant のインストール

## **Exercise 2: Azure SQL Database へのオンプレミス データベースの移行**
所要時間：45分

この実習では、Microsoft Data Migration Assistant (DMA) を使用して、Azure SQL Database に移行するために ContosoInsurance データベースにアクセスします。この評価を実行すると、オンプレミス データベースと Azure SQL Database の間の機能等価性および互換性の問題の詳細を示すレポートが生成されます。
DMA を使用すると、新しいバージョンの SQL Server または Azure SQL Databaseのデータベース機能に影響する可能性のある互換性の問題を削除して最新のデータ プラットフォームにアップグレードできます。DMA では、ターゲット環境用のパフォーマンスおよび信頼性向上に関する推奨事項が提供され、スキーマ、データ、および含まれないオブジェクトをソース サーバーからターゲット サーバーに移行することが可能になります。

### 参考情報
- Data Migration Assistant の概要  
<https://docs.microsoft.com/ja-jp/sql/dma/dma-overview?view=azuresqldb-mi-current>

### **Task 1**: ContosoInsurance の構成
評価を開始する前に、SQL Server 2008 R2 インスタンスで ContosoInsurance データベースを構成する必要があります。このタスクでは、SQL Server 2008 R2 インスタンス上の ContosoInsurance データベースに対して SQL スクリプトを実行します。

### **Task 2**: Azure SQL Database への移行の評価の実行
Contoso は、評価を実行して、Azure SQL Database にデータベースを移行する際に対処する必要のある潜在的な問題を識別したいと考えています。このタスクでは、Microsoft Data Migration Assistant (DMA) を使用して、Azure SQL Database に対して ContosoInsurance データベースの評価を実行します。

### **Task 3**: Data Migration Assistant を使用したデータベース スキーマの移行
評価結果をレビューしてデータベースを Azure SQL Database に移行できることを確認した後、  
Data Migration Assistant を使用してスキーマを Azure SQL Database に移行します。

### **Task 4**: SQL Server 2008 R2 仮想マシンの IP アドレスの取得
このタスクでは、Azure Cloud Shell を使用して SqlServer2008 VM の IP アドレスを取得します。  
このアドレスは、DMS から SqlServer2008 VM に接続するために必要です。

### **Task 5**: Azure Database Migration Service を使用したデータベースの移行
この時点で、DMAを使用したデータベーススキーマの移行が完了しています。このタスクでは、Azure Database Migration Service を使用して ContosoInsurance データベースのデータを新しい Azure SQL Database に以降します。
Azure Database Migration Service はマイクロソフトの既存のツールおよびサービスのいくつかの機能と統合して、包括的で高可用性を備えたデータベース移行ソリューションを提供します。このサービスは Data Migration Assistant を使用して、移行を実行する前に必要な変更をガイドする推奨事項を提供する評価レポートを生成します。移行プロセスを開始する準備ができたら、必要なすべての手順が Azure Database Migration Service によって実行されます。

## **Exercise 3: データベースのアップグレード後のセキュリティ強化**
この実習では、Azure SQL Database のいくつかのセキュリティ機能を確認し、Azure SQL Database を利用する際のセキュリティの利点をレビューします。SQL Database 向け Advanced Data Security (ADS) は、機密データの検出と分類、潜在的なデータベースの脆弱性の検出と緩和、およびデータベースに対する脅威を示す可能性のある異常なアクティビティの検出に関する機能を始めとする高度なセキュリティ機能を提供します。

### 参考情報
- Azure SQL Database 向け Advanced Data Security  
<https://docs.microsoft.com/ja-jp/azure/sql-database/sql-database-advanced-data-security>
- SQL データの検出と分類  
<https://docs.microsoft.com/ja-jp/sql/relational-databases/security/sql-data-discovery-and-classification?view=sql-server-2017&tabs=t-sql>
- SQL の脆弱性評価サービス  
<https://docs.microsoft.com/ja-jp/azure/sql-database/sql-vulnerability-assessment>

### **Task 1**: データの検出と分類の構成
このタスクでは、Advanced Data Security の SQL データの検出と分類機能を確認します。データの検出と分類では、データベース内の機密データの検出、分類、ラベル付け、レポート作成を行うための新しいツールが導入されましたこの機能では、データベースだけでなく、データベース内のデータの保護を目的とした新しい SQL 情報保護パラダイムを構成する高度なサービスのセットが提供されます。最も機密性の高いデータ (ビジネス、財務、医療など) の検出と分類は、組織の情報保護の達成において極めて重要な役割を果たすことができます。

### **Task 2**: Advanced Data Security の脆弱性評価のレビュー
このタスクでは、ContosoInsurance データベースに対して ADS で生成された評価レポートをレビューします。SQL の脆弱性評価サービスは、セキュリティ状態を可視化し、セキュリティの問題を解決してデータベース セキュリティを強化するための手順を示すサービスです。

### **Task 3**: 動的データ マスクの有効化
このタスクでは、Azure SQL Database  で動的データ マスク (DDM) を有効化して、クエリー結果からのデータベース内の機密データへのアクセスを制限します。この機能ではアプリケーション レイヤーへの影響を最小限に抑えた状態で公開する機密データを指定できるので、機密データへの不正アクセスの防止に役立ちます。これはポリシー ベースのセキュリティ機能で、指定したデータベース フィールドに対するクエリーの結果セット内の機密データを非表示にします。データベース内のデータは変更されることはありません。

## **Exercise 4: Key Vault の構成**
所要時間：15分

セキュリティ強化の一環として、Contoso は、アプリケーション構成ファイルでプレーン テキストとして表示されないように、アプリケーション シークレットをセキュアな方法で格納することを求めています。この実習では、Azure に移行した後に Contoso の Web アプリケーションと API アプリケーションのアプリケーション シークレットをセキュアに格納する Azure Key Vault を構成します。

### **Task 1**: Key Vault アクセス ポリシーの追加
このタスクでは、Key Vault にアクセス ポリシーを追加してアカウントでシークレットを作成します。

### **Task 2**: SQL 接続文字列を格納する新しいシークレットの作成
このタスクでは、Azure SQL Database の ContosoInsurance データベースへの接続文字列をキー コンテナーにシークレットとして追加します。

### **Task 3**: サービス プリンシパルの作成
このタスクでは、Azure Cloud Shell および Azure コマンド ライン インターフェイス (CLI) を使用して、Azure Key Vault に格納されたシークレットへのアクセスを Web アプリと API アプリに提供するために使用する Azure Active Directory (Azure AD) アプリケーションおよびサービス プリンシパル (SP) を作成します。  
>**重要**: このタスクを完了するには、Azure AD テナント内でアプリケーションの作成と役割の割り当てを行うアクセス許可が必要です。

### **Task 4**: Key Vault へのサービス プリンシパル アクセスの割り当て
このタスクでは、前の手順で作成したサービス プリンシパルにリソース グループの Reader の役割を割り当てます。その後、アクセス ポリシーをキー コンテナーに追加して、キー コンテナーに格納されたシークレットの読み取りを許可します。

## **Exercise 5: Azure App Services への Web API の展開**  
所要時間：45分  
  
Contoso の開発者はクラウドへの社内アプリの移行作業を続けています。開発者からは、ASP.NET Core を使用して開発されたソリューションが提供されています。アプリを Azure に展開し、新しいアプリ サービスと通信するための構成を行う準備がほとんど整いました。要求されたサービスは既にプロビジョニングされているので、残りの作業は Azure Key Vault を API に統合し、アプリケーション レベルの構成設定を適用して Visual Studio ソリューションからアプリを展開することです。このタスクでは、Azure Portal を使用してアプリケーション設定を Web API に適用します。アプリケーション設定が完了したら、 Web App と API App を Visual Studio から Azure に展開します。  
  
### **Task 1**: Visual Studio でソリューションを開く  
このタスクでは、`Contoso` スターター ソリューションを Visual Studio で開きます。Visual Studio ソリューションには以下のプロジェクトが含まれています。   
  
  - **Contoso.Azure**: ソリューション内で Azure サービスと通信するためにその他のプロジェクトで使用されるヘルパー クラスを含む共通のライブラリ  
  - **Contoso.Data**: データ アクセス オブジェクトを含むライブラリ  
  - **Contoso.FunctionApp**: Blob ストレージから保険契約ドキュメントを取得するために使用される Azure Function を含みます  
  - **Contoso.Web**: ASP.NET Core 2.2 PolicyConnect Web アプリケーション  
  - **Contoso.WebApi**: データベースと通信するために Web アプリケーションで使用される ASP.NET Core 2.2 Web API  
  
  1. ファイル エクスプローラーで `C:\MCW\MCW-App-modernization-master\Hands-on lab\lab-files\src` に移動し、`Contoso.sln` ファイルをダブルクリックしてソリューションを Visual Studio で開く
 
     <img src="images/E5-T1-1OpenSln.PNG" />
  
  2. ファイルを開く方法を尋ねるメッセージが表示されたら **Visual Studio 2019** を選択し**OK**を選択  
   
     <img src="images/E5-T1-2SelectOpen.PNG" />  

  3. Azure アカウントの資格情報を使用して Visual Studio にサインイン  
   
     <img src="images/E5-T1-3VSsignin.PNG" />  
  
  4. セキュリティ警告メッセージが表示された場合、**ソリューション内のすべてのプロジェクトに対して確認メッセージを表示する**ボックスをオフにして**OK**を選択
  
     <img src="images/E5-T1-4SecurityCheck.PNG" />  
  
### **Task 2**: Key Vault を使用するための Web API の更新  
このタスクでは、アプリケーション シークレットの格納と取得を目的として Azure Key Vault を使用するために `Contoso.WebApi` プロジェクトを更新します。接続情報を `Contoso.WebApi` プロジェクトの `appsettings.json` ファイルに追加し、いくつかのコードを追加して Azure Key Vault の使用を有効化します。  
  > Key Vault との対話を有効化するために必要な NuGet パッケージはプロジェクト内で既に参照されています。追加されているパッケージは `Microsoft.Extensions.Configuration.AzureKeyVault` です。  
  
  1. Visual Studio のソリューション エクスプローラーで `Contoso.WebApi` プロジェクトを展開し `Program.cs` ファイルをダブルクリックして開く  
    
     <img src="images/.PNG" />  
    
  2. `Program.cs` ファイルで `CreateWebHostBuilder` メソッド内の `TODO #1 ブロック` (23 行目) を見つける  
    
     <img src="images/.PNG" />  
    
  3. 次のコードを使用してブロック内のコードを完了し Key Vault を構成に追加し Key Vault に適切な接続情報を提供  　
     
     > config.AddAzureKeyVault(  
           KeyVaultConfig.GetKeyVaultEndpoint(buildConfig["KeyVaultName"]),  
           buildConfig["KeyVaultClientId"],  
           buildConfig["KeyVaultClientSecret"]  
      );  
      @@@表示の段落を整える  
    
  4. `Program.cs` を保存し更新された `CreateWebHostBuilder` メソッドは次のようになる  
    
     <img src="images/.PNG" />  
    
  5. 次に `Contoso.WebApi` プロジェクトの `Startup.cs` ファイルを更新するためにソリューション エクスプローラーでこのファイルをダブルクリック  
    
  6. 前の実習では、Azure SQL Database の接続文字列を Key Vault に追加し、シークレットに `SqlConnectionString` という名前を割り当てた。次は以下のコードを使用して、`Startup.cs` ファイルの `Configuration` プロパティ内の `TODO #2` ブロック (38 行目) を更新する。この更新により、アプリケーションでシークレット名を使用して Key Vault から接続文字列を取得することができる  
    
     <img src="images/.PNG" />  
     
     > services.AddDbContext<ContosoDbContext>(options =>  
           options.UseSqlServer(Configuration["SqlConnectionString"]));  
     @@@実表示の段落を整える
  
    
  7. `Startup.cs` を保存し更新された `Configuration` プロパティは次のようになる  
    
     <img src="images/.PNG" /> 
    
  8. これで Web API が完全に構成され、Azure Key Vault からシークレットを取得できるようになる  
    
### **Task 3**: Azure 内の API App への Key Vault 構成セクションのコピー
Web API を Azure に展開する前に、必要なアプリケーション設定を Azure API App の構成に追加する必要があります。このタスクでは、API App の構成エディターを使用して、Key Vault への接続と Key Vault からのシークレットの取得を行うために必要な構成設定を追加します。

### **Task 4**: Azure への API の展開
このタスクでは、Visual Studio を使用して API プロジェクトを Azure の API App に展開します。

## **Exercise 6: Azure App Services への Web アプリケーションの展開**
この実習では、Contoso.Web Web アプリケーションを更新して新しく展開した API App に接続し、Web App を Azure App Services に展開します。

### **Task 1**: Web App のアプリケーション設定への API App URL の追加
所要時間：10分

このタスクでは、Azure Cloud Shell および Azure CLI を使用して発行済み API App の URL を Web App のアプリケーション設定に追加し、Web App が API App と連動するための準備を行います。

### **Task 2**: Azure への Web アプリケーションの展開
このタスクでは、Contoso.Web アプリケーションを Azure Web App に発行します。

## **Exercise 7: Blob ストレージへの保険契約ドキュメントのアップロード**
所要時間：10分

現在、Contoso では、スキャンしたすべての PDF ファイルをローカル ネットワーク内に格納しています。Contoso は、PDF ファイルをワークフローからクラウドに自動的に格納したいと考えています。この実習では、Blob コンテナーにファイルを格納するためのストレージ アカウントを準備します。次に、既存の PDF ファイルを一括アップロードします。

参考情報
- AzCopy  
<https://docs.microsoft.com/ja-jp/azure/storage/common/storage-use-azcopy-v10>
### **Task 1**: PDF ファイルを格納するコンテナーの作成
このタスクでは、ストレージ アカウントにスキャン済み保険契約ドキュメントを格納する新しい Blob コンテナーを作成します。

### **Task 2**: SAS トークンの作成
このタスクでは、ストレージ アカウントの SAS (Shared Access Signature) トークンを生成します。これは後の実習で Azure Function を使用して Azure ストレージの policies コンテナーからファイルを取得するために使用します。

### **Task 3**: AzCopy を使用した Blob ストレージへの PDF の一括アップロード
このタスクでは、AzCopy を使用して PDF ファイルを "オンプレミス" の場所から Azure ストレージの policies コンテナーにコピーします。

## **Exercise 8: PDF にアクセスするための Azure Functions の作成**
所要時間：30分

Contoso はアプリケーションを準備するためにいくつかの更新を行いましたが、API に組み込むことのできていない機能がいくつかあります。Contoso は、PoC (概念実証) API ソリューションをセットアップして、アプリケーションのユーザーが Azure ストレージ アカウントから保険契約情報を直接取得できるようにしたいと考えています。この実習では、Azure Functions を作成し、サーバーレス テクノロジを使用して、この機能を有効にします。

### **Task 1**:  Azure Functions へのアプリケーション設定の追加
このタスクでは、Azure Cloud Shell および Azure CLI を使用して、ストレージ アカウントの policies コンテナー URL および SAS トークン値を Function App のアプリケーション設定に追加し、新しい関数と連動するよう Azure Function App を準備します。

### **Task 2**: プロジェクト環境変数の追加
関数は環境変数を使用して構成設定を取得します。関数をローカルでテストするには、これらの設定を開発用マシンでユーザー環境変数として追加するか、プロジェクト設定に追加する必要があります。

### **Task 3**: Visual Studio での Azure Functions の作成
このタスクでは、Visual Studio を使用して Azure Functions を作成します。この関数は、Blob ストレージから保険契約ドキュメントを取得するサーバーレス API として機能します。

### **Task 4**: ローカル環境での関数のテスト
このタスクでは、Visual Studio デバッガ―から関数をローカルで実行し、適切に構成されていること、およびストレージ アカウントの policies コンテナーからドキュメントを取得できることを確認します。

### **Task 5**: Azure Functions への関数の展開
このタスクでは、関数を Azure Functions に展開します。Azure Functions では、Web アプリケーションが関数を使用して契約ドキュメントを取得します。

### **Task 6**: Azure Functions での Application Insights の有効化
このタスクでは、Application Insights を Azure Functions に追加し、関数に対するリクエストのインサイトを収集します。

### **Task 7**: Web Apps のアプリケーション設定への Azure Functions URL の追加
このタスクでは、Azure Functions の URL を Web App のアプリケーション設定に追加します。

### **Task 8**: Web アプリからドキュメント取得のテスト
このタスクでは、PolicyConnect Web アプリを開いて保険契約ドキュメントをダウンロードします。以前の手順ではページが見つからないことを示すエラーが表示されていました。

### **Task 9**: ライブ メトリックス ストリームの表示

## **Exercise 9: 保険契約ドキュメントへのフルテキスト検索機能の追加**
所要時間：15分

Contoso は保険契約ドキュメントのフルテキスト検索を実行する機能を実装したいと考えています。以前、Contoso では、使用可能な状態でドキュメントから情報を取得することができませんでしたが、『Azure Search Service でのコグニティブ検索』で紹介されている技法を検索インデックスで活用することを検討しています。この実習では、Blob ストレージ コンテナーのコグニティブ検索を構成します。

参考情報

- Azure Cognitive Search における AI の概要  
<https://docs.microsoft.com/ja-jp/azure/search/cognitive-search-concept-intro>
### **Task 1**: ストレージ アカウントへの Azure Search の追加

### **Task 2**: 検索結果のレビュー
このタスクでは、検索インデックスに対してクエリーを実行し、コグニティブ検索によって保険契約ドキュメントに追加されたエンリッチメントをレビューします。

## **Exercise 10: API Management への API のインポートと公開**
所要時間：30分

この実習では、API Management から API App および Azure Functions API エンドポイントを発行します。

### **Task 1**: API App のインポート
このタスクでは、OpenAPI 仕様を使用して、API App に関連付けられた Swagger 定義を活用し API Management に API App をインポートします。

### **Task 2**: Azure Functions のインポート
このタスクでは、Azure Functions を API Management にインポートします。

### **Task 3**: 開発者ポータルからの API キーの取得
このタスクでは、開発者ポータルで API を確認してキーを取得します。開発者ポータルでは、API およびエンドポイントのリストに加えて、API とエンドポイントに関する有益な情報が表示されます。

### **Task 4**: API Management エンドポイントを使用するための Web App の更新
このタスクでは、Azure Cloud Shell および Azure CLI を使用して、PolicyConnect Web App の Url および PolicyDocumentsPath 設定を更新します。API Management アクセス キーに新しい設定も追加します。

## **Exercise 11: PowerApps でのアプリの作成**
所要時間：15分

モバイル アプリの作成には長い開発プロセスが必要なので、Contoso は PowerApps を使用してモバイル アプリケーションを作成し、現在のアプリでは提供されていない機能を迅速に追加することが検討されています。このシナリオでは、現在のアプリでは実行できない保険契約の値 (Silver、Gold、Platinum など) を編集する機能を実装します。このタスクでは、PowerApps で作成した新しいアプリを実行し、ContosoInsurance データベースに接続して基本的な CRUD (Create、Read、Update、および Delete) 操作を Policies テーブルに対して実行します。

### **Task 1**: PowerApps アカウントへのサインアップ

### **Task 2**: 新しい SQL 接続の作成

### **Task 3**: 新しいアプリの作成

### **Task 4**: アプリの設計

### **Task 5**: アプリ設定の編集とアプリの実行

## **ワークショップ後の作業**
ワークショップで使用した Azure リソースを削除します。

### **Task 1**: リソース グループの削除

### **Task 2**: Contoso-apps サービス プリンシパルの削除

***
このドキュメントに含まれているURL およびその他のインターネット Web サイトの参照を始めとする情報は予告なく変更されることがあります。別途明示されている場合を除き、本書内で例として使用されている会社、組織、製品、ドメイン名、電子メール アドレス、ロゴ、人物、場所、およびイベントは架空のもので、実在する企業、組織、製品、ドメイン名、電子メール アドレス、ロゴ、人、場所、または人とは関係ありません。ユーザーは該当するすべての著作権法に従う責任があります。このドキュメントを使用する場合は、適用される著作権関連の法律に従っていただくものとします。このドキュメントのいかなる部分も、米国 Microsoft Corporation の書面による許諾を受けることなく、その目的を問わず、どのような形態であっても、複製または譲渡することは禁じられています。ここでいう形態とは、複写や記録など、電子的な、または物理的なすべての手段を含みます。ただしこれは、著作権法上のお客様の権利を制限するものではありません。
マイクロソフトは、この文書に記載されている事項に関して、特許、申請中特許、商標、著作権、および他の知的財産権を所有する場合があります。別途マイクロソフトのライセンス契約上に明示の規定のない限り、このドキュメントはこれらの特許、商標、著作権、またはその他の無体財産権に関する権利をユーザーに許諾するものではありません。
製造業者名、製品名、または URL は情報提供の目的でのみ使用されています。明示、黙示、または法律の規定にかかわらず、これらの製造業者やマイクソフト テクノロジを含む製品の使用に関してマイクロソフトはいかなる責任も負わないものとします。製造業者または製品が記載されていることにより、マイクロソフトによる製造業者または製品の保証が示唆されるものではありません。サード パーティのサイトへのリンクが記載されている可能性があります。そのようなサイトはマイクロソフトの管理下にないので、マイクロソフトは、リンク先のサイトのコンテンツやリンク先のサイトに含まれるリンク、またはそのようなサイトの更新に関していかなる責任も負わないものとします。マイクロソフトは、リンク先のサイトから提供されるウェブキャストまたはその他の形式の送信に責任を負わないものとします。マイクロソフトは、これらのリンクをユーザーの利便性のみを目的として提供しています。含まれるリンクは、サイトやそこに含まれる製品に対するマイクロソフトの保証を示唆するものではありません。

&copy; 2020 Microsoft Corporation. All rights reserved.

マイクロソフトおよび <https://www.microsoft.com/en-us/legal/intellectualproperty/Trademarks/Usage/General.aspx> に記載されている商標は、Microsoft グループ企業の商標ですその他すべての商標は各社が所有しています。
