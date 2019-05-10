---
title: Windows Communication Foundation での Internet Information Services 7.0 の構成
ms.date: 03/30/2017
ms.assetid: 1050d395-092e-44d3-b4ba-66be3b039ffb
ms.openlocfilehash: 6962ed1dccca6db2e55554459742adab210585ef
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64654989"
---
# <a name="configuring-internet-information-services-70-for-windows-communication-foundation"></a><span data-ttu-id="03305-102">Windows Communication Foundation での Internet Information Services 7.0 の構成</span><span class="sxs-lookup"><span data-stu-id="03305-102">Configuring Internet Information Services 7.0 for Windows Communication Foundation</span></span>

<span data-ttu-id="03305-103">Internet Information Services (IIS) 7.0 はモジュール設計になっており、必要なコンポーネントを選択してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="03305-103">Internet Information Services (IIS) 7.0 has a modular design that allows you to selectively install components that are required.</span></span> <span data-ttu-id="03305-104">この設計は、[!INCLUDE[wv](../../../../includes/wv-md.md)] で新しく導入されたマニフェスト ドリブンのコンポーネント テクノロジに基づいています。</span><span class="sxs-lookup"><span data-stu-id="03305-104">This design is based on the new manifest-driven componentization technology introduced in [!INCLUDE[wv](../../../../includes/wv-md.md)].</span></span> <span data-ttu-id="03305-105">個別にインストールする IIS 7.0 の 40 以上のスタンドアロン機能コンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="03305-105">There are more than 40 standalone feature components of IIS 7.0 that can be installed independently.</span></span> <span data-ttu-id="03305-106">これにより、IT プロフェッショナルは必要に応じてインストールをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="03305-106">This allows IT professionals to easily customize the installation as required.</span></span> <span data-ttu-id="03305-107">このトピックでは、Windows Communication Foundation (WCF) を使用するための IIS 7.0 の構成し、必要なコンポーネントを決定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="03305-107">This topic discusses how to configure IIS 7.0 for use with Windows Communication Foundation (WCF) and determine which components are required.</span></span>

## <a name="minimal-installation-installing-was"></a><span data-ttu-id="03305-108">最小インストール:WAS をインストールします。</span><span class="sxs-lookup"><span data-stu-id="03305-108">Minimal Installation: Installing WAS</span></span>
 <span data-ttu-id="03305-109">IIS 7.0 パッケージ全体の最小インストールでは、Windows プロセス アクティブ化サービス (WAS) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="03305-109">The minimal installation of the whole IIS 7.0 package is to install the Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="03305-110">スタンドアロン機能であり唯一の機能すべてに使用される IIS 7.0 からが[!INCLUDE[wv](../../../../includes/wv-md.md)]オペレーティング システム (Home Basic、Home Premium、Business、および Ultimate および Enterprise)。</span><span class="sxs-lookup"><span data-stu-id="03305-110">WAS is a standalone feature and it is the only feature from the IIS 7.0 that is available for all [!INCLUDE[wv](../../../../includes/wv-md.md)] operating systems (Home Basic, Home Premium, Business, and Ultimate and Enterprise).</span></span>

 <span data-ttu-id="03305-111">コントロール パネルの **プログラム**順にクリックします**オンまたはオフにする Windows 機能**の下にリストされている**プログラムと機能**、WAS コンポーネントがで示すように、次の図のようにリストします。</span><span class="sxs-lookup"><span data-stu-id="03305-111">From the Control Panel, click **Programs** and then click **Turn Windows features on or off** which is listed under **Programs and Features**, the WAS component is shown in the list as in the following illustration.</span></span>

 <span data-ttu-id="03305-112">![機能のオン/オフ ダイアログ](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")</span><span class="sxs-lookup"><span data-stu-id="03305-112">![Turn Features On or Off Dialog](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")</span></span>

 <span data-ttu-id="03305-113">この機能には、次のサブコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="03305-113">This feature has the following sub-components:</span></span>

- <span data-ttu-id="03305-114">.NET 環境</span><span class="sxs-lookup"><span data-stu-id="03305-114">.NET Environment</span></span>

- <span data-ttu-id="03305-115">構成 API</span><span class="sxs-lookup"><span data-stu-id="03305-115">Configuration APIs</span></span>

- <span data-ttu-id="03305-116">プロセス モデル</span><span class="sxs-lookup"><span data-stu-id="03305-116">Process Model</span></span>

 <span data-ttu-id="03305-117">WAS のルート ノードのみを選択するかどうか、**プロセス モデル**サブ ノードは既定でオンにします。</span><span class="sxs-lookup"><span data-stu-id="03305-117">If you select the root node of WAS, only the **Process Model** sub-node is checked by default.</span></span> <span data-ttu-id="03305-118">このインストールでは Web サーバーをサポートしないため、WAS のみをインストールすることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="03305-118">Please note that with this installation you are only installing WAS, because there is no support for a Web server.</span></span>

 <span data-ttu-id="03305-119">WCF または ASP.NET アプリケーション作業するために、確認、 **.NET 環境**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="03305-119">To make WCF or any ASP.NET application work, check the **.NET Environment** checkbox.</span></span> <span data-ttu-id="03305-120">これはすべての WAS コンポーネントがうまく動作するためには、WCF と ASP.NET に必要なことを意味します。</span><span class="sxs-lookup"><span data-stu-id="03305-120">This means that all of WAS components are required to make WCF and ASP.NET to work well.</span></span> <span data-ttu-id="03305-121">これらのコンポーネントのいずれかを一度インストールすると、チェック ボックスは自動的にオンになります。</span><span class="sxs-lookup"><span data-stu-id="03305-121">These are automatically checked once you install any of those components.</span></span>

## <a name="iis-70-default-installation"></a><span data-ttu-id="03305-122">IIS 7.0:既定のインストール</span><span class="sxs-lookup"><span data-stu-id="03305-122">IIS 7.0: Default Installation</span></span>
 <span data-ttu-id="03305-123">チェックして、**インターネット インフォメーション サービス**機能は、一部のサブ ノードは次の図に示すように自動的にチェックします。</span><span class="sxs-lookup"><span data-stu-id="03305-123">By checking the **Internet Information Services** feature, some of the sub-nodes are automatically checked as shown in the following illustration.</span></span>

 <span data-ttu-id="03305-124">![IIS 7.0 機能の既定の設定](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")</span><span class="sxs-lookup"><span data-stu-id="03305-124">![Default settings for IIS 7.0 features](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")</span></span>

 <span data-ttu-id="03305-125">これは、IIS 7.0 の既定のインストールです。</span><span class="sxs-lookup"><span data-stu-id="03305-125">This is the default installation of IIS 7.0.</span></span> <span data-ttu-id="03305-126">このインストールにより、サービスの静的コンテンツ (HTML ページやその他のコンテンツ) を IIS 7.0 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="03305-126">With this installation, you can use IIS 7.0 to service static content (such as HTML pages and other content).</span></span> <span data-ttu-id="03305-127">ただし、ASP.NET または CGI アプリケーションまたは WCF サービスをホストを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="03305-127">However, you cannot run ASP.NET or CGI applications or host WCF services.</span></span>

## <a name="iis-70-installation-with-aspnet-support"></a><span data-ttu-id="03305-128">IIS 7.0:ASP.NET のサポートを使用したインストール</span><span class="sxs-lookup"><span data-stu-id="03305-128">IIS 7.0: Installation with ASP.NET Support</span></span>
 <span data-ttu-id="03305-129">ASP.NET が IIS 7.0 で動作させる ASP.NET をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="03305-129">You must install ASP.NET to make ASP.NET work on IIS 7.0.</span></span> <span data-ttu-id="03305-130">確認後**ASP.NET**画面に次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="03305-130">After checking **ASP.NET**, your screen should look like the following illustration.</span></span>

 <span data-ttu-id="03305-131">![Asp.NET の設定に必要な](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")</span><span class="sxs-lookup"><span data-stu-id="03305-131">![Asp.NET required settings](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")</span></span>

 <span data-ttu-id="03305-132">これは、WCF と ASP.NET の両方のアプリケーションを IIS 7.0 で動作するための最低限の環境です。</span><span class="sxs-lookup"><span data-stu-id="03305-132">This is the minimal environment for both WCF and ASP.NET applications to work in IIS 7.0.</span></span>

## <a name="iis-70-installation-with-iis-60-compatibility-components"></a><span data-ttu-id="03305-133">IIS 7.0:IIS 6.0 互換コンポーネントを使用したインストール</span><span class="sxs-lookup"><span data-stu-id="03305-133">IIS 7.0: Installation with IIS 6.0 Compatibility Components</span></span>
 <span data-ttu-id="03305-134">Visual Studio 2005 またはいくつか他の自動化スクリプトまたは IIS 6.0 メタベース API を使用した仮想アプリケーションの構成のツール (Adsutil.vbs) などのシステムで IIS 7.0 をインストールするときに、IIS 6.0 をチェックすることを確認**スクリプト ツール**.</span><span class="sxs-lookup"><span data-stu-id="03305-134">When installing IIS 7.0 on a system with Visual Studio 2005 or some other automation scripts or tools (such as Adsutil.vbs) that configure virtual applications that use IIS 6.0 Metabase API, ensure that you check the IIS 6.0 **Scripting Tools**.</span></span> <span data-ttu-id="03305-135">IIS 6.0 の他のサブ ノードを自動的にチェックし**互換性のある管理**します。</span><span class="sxs-lookup"><span data-stu-id="03305-135">This automatically checks the other sub-nodes of IIS 6.0 **Management Compatibility**.</span></span> <span data-ttu-id="03305-136">次の図は、これが完了した後、画面を示しています。</span><span class="sxs-lookup"><span data-stu-id="03305-136">The following illustration shows the screen after this is done:</span></span>

 <span data-ttu-id="03305-137">![IIS 6.0 管理互換設定](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")</span><span class="sxs-lookup"><span data-stu-id="03305-137">![IIS 6.0 Management Compatibility Settings](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")</span></span>

 <span data-ttu-id="03305-138">このインストールにより、Web 上の IIS 7.0、ASP.NET および WCF の機能と使用可能なサンプルを使用するために必要なすべてのものがあります。</span><span class="sxs-lookup"><span data-stu-id="03305-138">With this installation, you have everything required to use IIS 7.0, ASP.NET and WCF features and samples available on the Web.</span></span>

## <a name="request-limits"></a><span data-ttu-id="03305-139">要求の制限</span><span class="sxs-lookup"><span data-stu-id="03305-139">Request Limits</span></span>
 <span data-ttu-id="03305-140">IIS 7.0 がインストールされた [!INCLUDE[wv](../../../../includes/wv-md.md)] では、`maxUri` および `maxQueryStringSize` の設定の既定値が変更されています。</span><span class="sxs-lookup"><span data-stu-id="03305-140">On [!INCLUDE[wv](../../../../includes/wv-md.md)] with IIS 7 the default value of the `maxUri` and `maxQueryStringSize` settings have been changed.</span></span> <span data-ttu-id="03305-141">既定では、IIS 7.0 における要求のフィルター処理で使用できる文字数は、URL が 4096 文字、クエリ文字列が 2048 文字です。</span><span class="sxs-lookup"><span data-stu-id="03305-141">By default, request filtering in IIS 7.0 allows a URL length of 4096 characters and a query string length of 2048 characters.</span></span> <span data-ttu-id="03305-142">これらの既定値を変更するには、App.config ファイルに次の XML を追加します。</span><span class="sxs-lookup"><span data-stu-id="03305-142">To change these defaults add the following XML to your App.config file.</span></span>

```xml
 <system.webServer>
    <security>
        <requestFiltering>
            <requestLimits maxUrl="8192" maxQueryString="8192" />
        </requestFiltering>
    </security>
 </system.webServer>
 ```

## <a name="see-also"></a><span data-ttu-id="03305-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="03305-143">See also</span></span>

- [<span data-ttu-id="03305-144">WAS アクティベーション アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="03305-144">WAS Activation Architecture</span></span>](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)
- [<span data-ttu-id="03305-145">WCF で使用するための WAS を設定する</span><span class="sxs-lookup"><span data-stu-id="03305-145">Configuring WAS for Use with WCF</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)
- [<span data-ttu-id="03305-146">方法: インストールし、WCF アクティブ化コンポーネントの構成</span><span class="sxs-lookup"><span data-stu-id="03305-146">How to: Install and Configure WCF Activation Components</span></span>](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)
- [<span data-ttu-id="03305-147">AppFabric のホスティング機能</span><span class="sxs-lookup"><span data-stu-id="03305-147">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
