---
title: WPF ホスト (PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: 64ba1261134184f22e9faf157ca70e3471e3b3cb
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636251"
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="10d9d-102">WPF ホスト (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="10d9d-102">WPF Host (PresentationHost.exe)</span></span>
<span data-ttu-id="10d9d-103">Windows Presentation Foundation (WPF) ホスト (プレゼンテーションホスト .exe) は、互換性のあるブラウザー (Microsoft Internet Explorer 6 以降を含む) で WPF アプリケーションをホストできるようにするアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="10d9d-103">Windows Presentation Foundation (WPF) Host (PresentationHost.exe) is the application that enables WPF applications to be hosted in compatible browsers (including Microsoft Internet Explorer 6 and later).</span></span> <span data-ttu-id="10d9d-104">既定では、Windows Presentation Foundation (WPF) ホストは、ブラウザーでホストされる WPF コンテンツのシェルおよび MIME ハンドラーとして登録されます。これには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="10d9d-104">By default, Windows Presentation Foundation (WPF) Host is registered as the shell and MIME handler for browser-hosted WPF content, which includes:</span></span>  
  
- <span data-ttu-id="10d9d-105">Loose (コンパイルされていない) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイル (.xaml)。</span><span class="sxs-lookup"><span data-stu-id="10d9d-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
- <span data-ttu-id="10d9d-106">XAML ブラウザーアプリケーション (XBAP) (xbap)。</span><span class="sxs-lookup"><span data-stu-id="10d9d-106">XAML browser application (XBAP) (.xbap).</span></span>  
  
 <span data-ttu-id="10d9d-107">これらの種類のファイルについては、Windows Presentation Foundation (WPF) ホスト:</span><span class="sxs-lookup"><span data-stu-id="10d9d-107">For files of these types, Windows Presentation Foundation (WPF) Host:</span></span>  
  
- <span data-ttu-id="10d9d-108">Windows Presentation Foundation (WPF) コンテンツをホストするために、登録されている HTML ハンドラーを起動します。</span><span class="sxs-lookup"><span data-stu-id="10d9d-108">Launches the registered HTML handler to host the Windows Presentation Foundation (WPF) content.</span></span>  
  
- <span data-ttu-id="10d9d-109">必要な共通言語ランタイム (CLR) アセンブリと Windows Presentation Foundation (WPF) アセンブリの適切なバージョンを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="10d9d-109">Loads the right versions of the required common language runtime (CLR) and Windows Presentation Foundation (WPF) assemblies.</span></span>  
  
- <span data-ttu-id="10d9d-110">展開のゾーンに適切なアクセス許可レベルが設定されるようにします。</span><span class="sxs-lookup"><span data-stu-id="10d9d-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="10d9d-111">このトピックでは、PresentationHost.exe で使用できるコマンド ライン パラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="10d9d-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="10d9d-112">使用状況</span><span class="sxs-lookup"><span data-stu-id="10d9d-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="10d9d-113">パラメーター</span><span class="sxs-lookup"><span data-stu-id="10d9d-113">Parameters</span></span>  
  
|<span data-ttu-id="10d9d-114">パラメータ</span><span class="sxs-lookup"><span data-stu-id="10d9d-114">Parameter</span></span>|<span data-ttu-id="10d9d-115">説明</span><span class="sxs-lookup"><span data-stu-id="10d9d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="10d9d-116">filename</span><span class="sxs-lookup"><span data-stu-id="10d9d-116">filename</span></span>|<span data-ttu-id="10d9d-117">アクティブにするファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="10d9d-117">The path of the file to be activated.</span></span> <span data-ttu-id="10d9d-118">は URI でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="10d9d-118">Can also be a URI.</span></span>|  
|<span data-ttu-id="10d9d-119">-debug</span><span class="sxs-lookup"><span data-stu-id="10d9d-119">-debug</span></span>|<span data-ttu-id="10d9d-120">アプリケーションをアクティブにする場合に、このアプリケーションをストアにコミットしたり、ストアから実行しません。</span><span class="sxs-lookup"><span data-stu-id="10d9d-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="10d9d-121">これは、ローカル ファイルをアクティブにする場合に限って使用できます。</span><span class="sxs-lookup"><span data-stu-id="10d9d-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="10d9d-122">-debugSecurityZoneURL \<url></span><span class="sxs-lookup"><span data-stu-id="10d9d-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="10d9d-123">指定された URL からアプリケーションが配置されているかのように、アプリケーションをデバッグする必要があることを示すために、URL 値と共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="10d9d-123">Used with a URL value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified URL.</span></span> <span data-ttu-id="10d9d-124">これは、展開ゾーンと起点サイトの両方を決定します。</span><span class="sxs-lookup"><span data-stu-id="10d9d-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="10d9d-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="10d9d-125">-embedding</span></span>|<span data-ttu-id="10d9d-126">OLE で必要になります。</span><span class="sxs-lookup"><span data-stu-id="10d9d-126">Required by OLE.</span></span> <span data-ttu-id="10d9d-127">`-event` パラメーターまたは `-debug` パラメーターを指定した場合、`-embedding` パラメーターは内部で設定されるため、指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="10d9d-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="10d9d-128">-event \<eventname></span><span class="sxs-lookup"><span data-stu-id="10d9d-128">-event \<eventname></span></span>|<span data-ttu-id="10d9d-129">この名前のイベントを開き、プレゼンテーションの cluster.exe が初期化され、WPF コンテンツをホストする準備ができたら、そのイベントを通知します。</span><span class="sxs-lookup"><span data-stu-id="10d9d-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host WPF content.</span></span> <span data-ttu-id="10d9d-130">PresentationHost.exe は、イベントを開く際にエラーが発生すると (そのイベントがまだ作成されていない場合など) 終了します。</span><span class="sxs-lookup"><span data-stu-id="10d9d-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="10d9d-131">-launchApplication \<url></span><span class="sxs-lookup"><span data-stu-id="10d9d-131">-launchApplication \<url></span></span>|<span data-ttu-id="10d9d-132">指定された URL からスタンドアロンの ClickOnce アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="10d9d-132">Launches a standalone ClickOnce application from the specified URL.</span></span> <span data-ttu-id="10d9d-133">.NET アプリケーションに関する Internet Explorer と WinINet のセキュリティポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="10d9d-133">Internet Explorer and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="10d9d-134">監視プロセス</span><span class="sxs-lookup"><span data-stu-id="10d9d-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="10d9d-135">シェル ハンドラー</span><span class="sxs-lookup"><span data-stu-id="10d9d-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="10d9d-136">MIME ハンドラー</span><span class="sxs-lookup"><span data-stu-id="10d9d-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="10d9d-137">Visual Studio によるデバッグ</span><span class="sxs-lookup"><span data-stu-id="10d9d-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="10d9d-138">Visual Studio によるゾーンでのデバッグ</span><span class="sxs-lookup"><span data-stu-id="10d9d-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="10d9d-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="10d9d-139">See also</span></span>

- [<span data-ttu-id="10d9d-140">Security</span><span class="sxs-lookup"><span data-stu-id="10d9d-140">Security</span></span>](../security-wpf.md)
