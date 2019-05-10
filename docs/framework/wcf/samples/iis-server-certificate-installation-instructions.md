---
title: インターネット インフォメーション サービス (IIS) サーバー証明書インストール手順
ms.date: 03/30/2017
ms.assetid: 11281490-d2ac-4324-8f33-e7714611a34b
ms.openlocfilehash: 728232c4e1d6309ae0cfacb407417173ece145da
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648356"
---
# <a name="internet-information-services-iis-server-certificate-installation-instructions"></a><span data-ttu-id="4b44e-102">インターネット インフォメーション サービス (IIS) サーバー証明書インストール手順</span><span class="sxs-lookup"><span data-stu-id="4b44e-102">Internet Information Services (IIS) Server Certificate Installation Instructions</span></span>
<span data-ttu-id="4b44e-103">インターネット インフォメーション サービス (IIS) と安全に通信するこのサンプルを実行するには、サーバー証明書を作成してインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b44e-103">To run the samples that securely communicate with Internet Information Services (IIS), you must create and install a server certificate.</span></span>  
  
## <a name="step-1-creating-certificates"></a><span data-ttu-id="4b44e-104">手順 1.</span><span class="sxs-lookup"><span data-stu-id="4b44e-104">Step 1.</span></span> <span data-ttu-id="4b44e-105">証明書の作成</span><span class="sxs-lookup"><span data-stu-id="4b44e-105">Creating Certificates</span></span>  
 <span data-ttu-id="4b44e-106">コンピューターの証明書を作成するには、管理者特権で Visual Studio の開発者コマンド プロンプトを開きし、の各 IIS をセキュリティで保護された通信を使用するサンプルに含まれている Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="4b44e-106">To create a certificate for your computer, open a Developer Command Prompt for Visual Studio with administrator privileges and run the Setup.bat that is included in each of the samples that use secure communication with IIS.</span></span> <span data-ttu-id="4b44e-107">このバッチ ファイルを実行する前に、Makecert.exe を含むフォルダがパスに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4b44e-107">Ensure that the path includes the folder that contains Makecert.exe before you run this batch file.</span></span> <span data-ttu-id="4b44e-108">Setup.bat で証明書の作成に使用されるコマンドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4b44e-108">The following command is used to create the certificate in Setup.bat.</span></span>  
  
```  
makecert -sr LocalMachine -ss My -n CN=ServiceModelSamples-HTTPS-Server -sky exchange -sk ServiceModelSamples-HTTPS-Key  
```  
  
## <a name="step-2-installing-certificates"></a><span data-ttu-id="4b44e-109">手順 2.</span><span class="sxs-lookup"><span data-stu-id="4b44e-109">Step 2.</span></span> <span data-ttu-id="4b44e-110">証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="4b44e-110">Installing Certificates</span></span>  
 <span data-ttu-id="4b44e-111">先ほど作成した証明書をインストールするために必要な手順は、使用している IIS のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="4b44e-111">The steps required to install the certificates you just created depend on which version of IIS you are using.</span></span>  
  
#### <a name="to-install-iis-on-iis-51-windows-xp-and-iis-60-windows-server-2003"></a><span data-ttu-id="4b44e-112">IIS 5.1 (Windows XP) および IIS 6.0 (Windows Server 2003) に証明書をインストールするには</span><span class="sxs-lookup"><span data-stu-id="4b44e-112">To install IIS on IIS 5.1 (Windows XP) and IIS 6.0 (Windows Server 2003)</span></span>  
  
1. <span data-ttu-id="4b44e-113">インターネット インフォメーション サービス マネージャー MMC スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="4b44e-113">Open the Internet Information Services Manager MMC Snap-In.</span></span>  
  
2. <span data-ttu-id="4b44e-114">既定の Web サイトを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="4b44e-114">Right-click the default Web site and select **Properties**.</span></span>  
  
3. <span data-ttu-id="4b44e-115">選択、**ディレクトリ セキュリティ**タブ。</span><span class="sxs-lookup"><span data-stu-id="4b44e-115">Select the **Directory Security** tab.</span></span>  
  
4. <span data-ttu-id="4b44e-116">をクリックして、**サーバー証明書**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b44e-116">Click the **Server Certificate** button.</span></span> <span data-ttu-id="4b44e-117">Web サーバー証明書ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="4b44e-117">The Web Server Certificate Wizard starts.</span></span>  
  
5. <span data-ttu-id="4b44e-118">ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="4b44e-118">Complete the wizard.</span></span> <span data-ttu-id="4b44e-119">証明書を割り当てるオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b44e-119">Select the option to assign a certificate.</span></span> <span data-ttu-id="4b44e-120">表示される証明書の一覧から ServiceModelSamples-HTTPS-Server 証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b44e-120">Select the ServiceModelSamples-HTTPS-Server certificate from the list of certificates that are displayed.</span></span>  
  
     <span data-ttu-id="4b44e-121">![証明書ウィザードの IIS](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span><span class="sxs-lookup"><span data-stu-id="4b44e-121">![IIS Certificate Wizard](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span></span>  
  
6. <span data-ttu-id="4b44e-122">HTTPS アドレスを使用して、ブラウザーでサービスへのアクセスをテスト`https://localhost/servicemodelsamples/service.svc`します。</span><span class="sxs-lookup"><span data-stu-id="4b44e-122">Test access to the service in a browser by using the HTTPS address `https://localhost/servicemodelsamples/service.svc`.</span></span>  
  
#### <a name="if-ssl-was-previously-configured-by-using-httpcfgexe"></a><span data-ttu-id="4b44e-123">Httpcfg.exe であらかじめ SSL が構成されている場合</span><span class="sxs-lookup"><span data-stu-id="4b44e-123">If SSL was previously configured by using Httpcfg.exe</span></span>  
  
1. <span data-ttu-id="4b44e-124">Makecert.exe を使用 (または Setup.bat を実行) して、サーバー証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="4b44e-124">Use Makecert.exe (or run Setup.bat) to create the server certificate.</span></span>  
  
2. <span data-ttu-id="4b44e-125">IIS マネージャを実行し、前の手順に従って証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="4b44e-125">Run the IIS manager and install the certificate according to the previous steps.</span></span>  
  
3. <span data-ttu-id="4b44e-126">クライアント プログラムに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="4b44e-126">Add the following line of code to the client program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4b44e-127">このコードが必要になるのは、Makecert.exe によって作成された証明書などをテストする場合のみです。</span><span class="sxs-lookup"><span data-stu-id="4b44e-127">This code is only required for test certificates such as those created by Makecert.exe.</span></span> <span data-ttu-id="4b44e-128">製品版のコードには、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="4b44e-128">It is not recommended for production code.</span></span>  
  
```  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
#### <a name="to-install-iis-on-iis-70-windows-vista-and-windows-server-2008"></a><span data-ttu-id="4b44e-129">IIS 7.0 (Windows Vista および Windows Server 2008) に証明書をインストールするには</span><span class="sxs-lookup"><span data-stu-id="4b44e-129">To install IIS on IIS 7.0 (Windows Vista and Windows Server 2008)</span></span>  
  
1. <span data-ttu-id="4b44e-130">**開始** メニューのをクリックして**実行**、入力**inetmgr**インターネット インフォメーション サービス (IIS) MMC スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="4b44e-130">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="4b44e-131">右クリックし、**既定の Web サイト**選択**バインドを編集しています.**</span><span class="sxs-lookup"><span data-stu-id="4b44e-131">Right-click the **Default Web Site** and select **Edit Bindings…**</span></span>  
  
3. <span data-ttu-id="4b44e-132">をクリックして、**追加**のボタン、**サイト バインド** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="4b44e-132">Click the **Add** button of the **Site Bindings** dialog box.</span></span>  
  
4. <span data-ttu-id="4b44e-133">選択**HTTPS**から、**型**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="4b44e-133">Select **HTTPS** from the **Type** drop-down list.</span></span>  
  
5. <span data-ttu-id="4b44e-134">選択、 **ServiceModelSamples-HTTPS サーバー**から、 **SSL 証明書**ドロップダウン リストをクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4b44e-134">Select the **ServiceModelSamples-HTTPS-Server** from the **SSL certificate** drop-down list and click **OK**.</span></span>  
  
6. <span data-ttu-id="4b44e-135">HTTPS アドレスを使用して、ブラウザーでサービスへのアクセスをテスト`https://localhost/servicemodelsamples/service.svc`します。</span><span class="sxs-lookup"><span data-stu-id="4b44e-135">Test access to the service in a browser by using the HTTPS address `https://localhost/servicemodelsamples/service.svc`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b44e-136">先ほどインストールしたテスト証明書は信頼された証明書ではないので、この証明書でセキュリティ保護されたローカル Web アドレスを参照した場合、Internet Explorer のセキュリティ警告がさらに発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="4b44e-136">Because the test certificate you have just installed is not a trusted certificate, you may encounter additional Internet Explorer security warnings when browsing to local Web addresses secured with this certificate.</span></span>  
  
## <a name="removing-certificates"></a><span data-ttu-id="4b44e-137">証明書の削除</span><span class="sxs-lookup"><span data-stu-id="4b44e-137">Removing Certificates</span></span>  
  
- <span data-ttu-id="4b44e-138">前に説明したようにインターネット インフォメーション サービス マネージャーを使用しますが、証明書またはバインディングを追加するのではなく削除します。</span><span class="sxs-lookup"><span data-stu-id="4b44e-138">Use the Internet Information Services Manager as previously directed, but remove the certificate or binding instead of adding it.</span></span>  
  
- <span data-ttu-id="4b44e-139">次のコマンドを使用して、コンピューターの証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="4b44e-139">Remove the computer certificate by using the following command.</span></span>  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:443  
    ```
