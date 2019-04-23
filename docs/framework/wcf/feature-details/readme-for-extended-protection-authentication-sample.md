---
title: 拡張保護認証のサンプルの ReadMe
ms.date: 03/30/2017
ms.assetid: 80bf2e97-398d-4db5-9040-d96478a2ccab
ms.openlocfilehash: 53592db03c88e673d529ef04f2fbc6e182897457
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979122"
---
# <a name="readme-for-extended-protection-authentication-sample"></a><span data-ttu-id="0ec09-102">拡張保護認証のサンプルの ReadMe</span><span class="sxs-lookup"><span data-stu-id="0ec09-102">ReadMe for Extended Protection Authentication Sample</span></span>
<span data-ttu-id="0ec09-103">拡張保護を攻撃者 (、「- the-中間」) がクライアントの資格情報をインターセプトし、クライアントの目的のサーバー上のセキュリティで保護されたリソースにアクセスする、中間の (MITM) 攻撃から保護するためのセキュリティ イニシアチブです。</span><span class="sxs-lookup"><span data-stu-id="0ec09-103">Extended Protection is a security initiative to protect against man-in-the-middle (MITM) attacks, in which an attacker (the "man-in-the-middle") intercepts a client’s credentials and uses them to access secure resources on the client’s intended server.</span></span>  
  
 <span data-ttu-id="0ec09-104">詳細については、次を参照してください。[認証の概要の拡張保護](../../../../docs/framework/wcf/feature-details/extended-protection-for-authentication-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="0ec09-104">For more information, see [Extended Protection for Authentication Overview](../../../../docs/framework/wcf/feature-details/extended-protection-for-authentication-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ec09-105">このサンプルは、IIS でホストされた場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="0ec09-105">This sample only works when hosted on IIS.</span></span> <span data-ttu-id="0ec09-106">このサンプルは HTTPS をサポートしないので、Visual Studio Development Server 上では機能しません。</span><span class="sxs-lookup"><span data-stu-id="0ec09-106">It does not work on Visual Studio Development Server because that does not support HTTPS.</span></span>  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0ec09-107">サンプルをセットアップしてビルドし、実行するには</span><span class="sxs-lookup"><span data-stu-id="0ec09-107">To Set Up, Build, and Run the Sample</span></span>  
  
1. <span data-ttu-id="0ec09-108">[プログラムの追加と削除] の [Windows の機能] から IIS をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0ec09-108">Install IIS on the machine from Add/Remove Programs -> Windows Features.</span></span>  
  
2. <span data-ttu-id="0ec09-109">Windows の機能では、Windows 認証を有効にします。インターネット インフォメーション サービス] の [World Wide Web サービスのセキュリティ]、[Windows 認証]-> [です。</span><span class="sxs-lookup"><span data-stu-id="0ec09-109">Turn on Windows Authentication in Windows features: Internet Information Services -> World Wide Web Services -> Security -> Windows Authentication.</span></span>  
  
3. <span data-ttu-id="0ec09-110">Windows の機能では、HTTP アクティブ化を有効にします。Microsoft .NET Framework 3.5.1 には、Windows Communication Foundation HTTP Activation]-> [です。</span><span class="sxs-lookup"><span data-stu-id="0ec09-110">Turn on HTTP Activation in Windows features: Microsoft .NET Framework 3.5.1 -> Windows Communication Foundation HTTP Activation.</span></span>  
  
4. <span data-ttu-id="0ec09-111">このサンプルを実行するには、サーバーとの安全なチャネルを確立する必要のあるクライアントが必要なので、インターネット インフォメーション サービス (IIS) マネージャーからインストールすることのできるサーバー証明書が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ec09-111">This sample requires the client to establish a secure channel with the server and so it requires the presence of a server certificate which can be installed from Internet Information Services (IIS) Manager.</span></span>  
  
    1.  <span data-ttu-id="0ec09-112">IIS マネージャーを開いて、[機能表示] タブから [サーバー証明書] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ec09-112">Open the IIS manager -> Server certificates (from the feature view tab).</span></span>  
  
    2.  <span data-ttu-id="0ec09-113">このサンプルをテストする目的で、自己署名証明書を作成できます </span><span class="sxs-lookup"><span data-stu-id="0ec09-113">For the purpose of testing this sample, you can create a self-signed certificate.</span></span> <span data-ttu-id="0ec09-114">(インターネット エクスプローラーで証明書の安全性に関するプロンプトが表示されないようにする場合は、信頼されたルート証明機関ストアに証明書をインストールできます)。</span><span class="sxs-lookup"><span data-stu-id="0ec09-114">(If you don’t want Internet Explorer to prompt you about the certificate not being secure, you can install it in the Trusted Certificate Root authority store).</span></span>  
  
5. <span data-ttu-id="0ec09-115">既定の Web サイトの操作ウィンドウに移動します。</span><span class="sxs-lookup"><span data-stu-id="0ec09-115">Go to the Actions pane for the Default Web site.</span></span> <span data-ttu-id="0ec09-116">[サイトの編集] の [バインド] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ec09-116">Click Edit Site -> Bindings.</span></span> <span data-ttu-id="0ec09-117">存在しない場合は、種類として HTTPS を追加します。ポート番号に 443 を指定し、前の手順で作成した SSL 証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0ec09-117">Add HTTPS as a type if it is not already present, with port number 443, and assign the SSL certificate created in the above step.</span></span>  
  
6. <span data-ttu-id="0ec09-118">サービスをビルドします。</span><span class="sxs-lookup"><span data-stu-id="0ec09-118">Build the service.</span></span> <span data-ttu-id="0ec09-119">(プロジェクト プロパティで指定されたビルド後のアクションから) IIS に仮想ディレクトリが作成され、サービスを Web ホスト サービスにするために必要な dll、.svc、および構成ファイルがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="0ec09-119">This creates a virtual directory in IIS for you (from the post build action specified in the project properties) and copies the dll, .svc and config files as needed for a service to be Web hosted.</span></span>  
  
7. <span data-ttu-id="0ec09-120">IIS マネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="0ec09-120">Open the IIS Manager.</span></span> <span data-ttu-id="0ec09-121">前の手順で作成した仮想ディレクトリ (ExtendedProtection) を右クリックして、[アプリケーションへの変換] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ec09-121">Right-click the virtual directory (ExtendedProtection) that you created in the previous step and select Convert to Application.</span></span>  
  
8. <span data-ttu-id="0ec09-122">この仮想ディレクトリの認証モジュールを IIS マネージャーで開き、Windows 認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0ec09-122">Open the Authentication module in IIS Manager for this virtual directory and enable Windows Authentication.</span></span>  
  
9. <span data-ttu-id="0ec09-123">このサンプルでは対応する ExtendedProtection 設定が [常に] に設定されているので、この仮想ディレクトリの Windows 認証の [詳細設定] を開き、[必須] に設定します。</span><span class="sxs-lookup"><span data-stu-id="0ec09-123">Open the Advanced Settings for Windows Authentication for this virtual directory and set it to Required, since, in the sample, the corresponding ExtendedProtection setting is set to Always.</span></span>  
  
10. <span data-ttu-id="0ec09-124">ブラウザー ウィンドウから URL にアクセスして、サービスをテストできます。</span><span class="sxs-lookup"><span data-stu-id="0ec09-124">You can test the service by accessing the URL from a browser window.</span></span> <span data-ttu-id="0ec09-125">コンピューター間でこの URL にアクセスする場合は、すべての受信 HTTP および HTTPS 通信に対してファイアウォールが開かれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0ec09-125">If you want to access this URL from a cross machine, make sure that the firewall is opened for all incoming HTTP and HTTPS connections.</span></span>  
  
11. <span data-ttu-id="0ec09-126">クライアントの構成ファイルを開き、完全なマシンの名前を指定、\<クライアント >-\<エンドポイント >-アドレス属性、<< full_machine_name >> を置換します。</span><span class="sxs-lookup"><span data-stu-id="0ec09-126">Open the client config file and provide a full machine name for the \<client> - \<endpoint> - address attribute, replacing <<full_machine_name>>.</span></span>  
  
12. <span data-ttu-id="0ec09-127">クライアントを実行します。</span><span class="sxs-lookup"><span data-stu-id="0ec09-127">Run the client.</span></span> <span data-ttu-id="0ec09-128">クライアントがセキュリティで保護されたチャネルを確立し、エンドポイント保護を使用してサービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="0ec09-128">The client communicates to the service by establishing a secure channel and using extended protection under the covers.</span></span>
