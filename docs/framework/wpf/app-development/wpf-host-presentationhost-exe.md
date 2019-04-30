---
title: WPF ホスト (PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: 586d306d0f375241c9382e1e24cf1af75b990ba9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62019166"
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="54bf1-102">WPF ホスト (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="54bf1-102">WPF Host (PresentationHost.exe)</span></span>
<span data-ttu-id="54bf1-103">Windows Presentation Foundation (WPF) のホスト (PresentationHost.exe) は、アプリケーションを使用[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]互換性のあるブラウザーでホストされるアプリケーション (を含む[!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)]以降)。</span><span class="sxs-lookup"><span data-stu-id="54bf1-103">Windows Presentation Foundation (WPF) Host (PresentationHost.exe) is the application that enables [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications to be hosted in compatible browsers (including [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] and later).</span></span> <span data-ttu-id="54bf1-104">シェルとして既定では、Windows Presentation Foundation (WPF) のホストが登録されていると[!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)]ハンドラーをブラウザーでホストされる[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]コンテンツが含まれます。</span><span class="sxs-lookup"><span data-stu-id="54bf1-104">By default, Windows Presentation Foundation (WPF) Host is registered as the shell and [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] handler for browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content, which includes:</span></span>  
  
- <span data-ttu-id="54bf1-105">Loose (コンパイルされていない) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイル (.xaml)。</span><span class="sxs-lookup"><span data-stu-id="54bf1-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
- [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] <span data-ttu-id="54bf1-106">(.xbap)。</span><span class="sxs-lookup"><span data-stu-id="54bf1-106">(.xbap).</span></span>  
  
 <span data-ttu-id="54bf1-107">これらの型では、Windows Presentation Foundation (WPF) のホストのファイル。</span><span class="sxs-lookup"><span data-stu-id="54bf1-107">For files of these types, Windows Presentation Foundation (WPF) Host:</span></span>  
  
- <span data-ttu-id="54bf1-108">登録されている起動[!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]Windows Presentation Foundation (WPF) コンテンツをホストするハンドラー。</span><span class="sxs-lookup"><span data-stu-id="54bf1-108">Launches the registered [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] handler to host the Windows Presentation Foundation (WPF) content.</span></span>  
  
- <span data-ttu-id="54bf1-109">必須の正しいバージョンを読み込みます[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]と Windows Presentation Foundation (WPF) のアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="54bf1-109">Loads the right versions of the required [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] and Windows Presentation Foundation (WPF) assemblies.</span></span>  
  
- <span data-ttu-id="54bf1-110">展開のゾーンに適切なアクセス許可レベルが設定されるようにします。</span><span class="sxs-lookup"><span data-stu-id="54bf1-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="54bf1-111">このトピックでは、PresentationHost.exe で使用できるコマンド ライン パラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="54bf1-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="54bf1-112">使用方法</span><span class="sxs-lookup"><span data-stu-id="54bf1-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="54bf1-113">パラメーター</span><span class="sxs-lookup"><span data-stu-id="54bf1-113">Parameters</span></span>  
  
|<span data-ttu-id="54bf1-114">パラメーター</span><span class="sxs-lookup"><span data-stu-id="54bf1-114">Parameter</span></span>|<span data-ttu-id="54bf1-115">説明</span><span class="sxs-lookup"><span data-stu-id="54bf1-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="54bf1-116">ファイル名</span><span class="sxs-lookup"><span data-stu-id="54bf1-116">filename</span></span>|<span data-ttu-id="54bf1-117">アクティブにするファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="54bf1-117">The path of the file to be activated.</span></span> <span data-ttu-id="54bf1-118">[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] も指定できます。</span><span class="sxs-lookup"><span data-stu-id="54bf1-118">Can also be a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>|  
|<span data-ttu-id="54bf1-119">-debug</span><span class="sxs-lookup"><span data-stu-id="54bf1-119">-debug</span></span>|<span data-ttu-id="54bf1-120">アプリケーションをアクティブにする場合に、このアプリケーションをストアにコミットしたり、ストアから実行しません。</span><span class="sxs-lookup"><span data-stu-id="54bf1-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="54bf1-121">これは、ローカル ファイルをアクティブにする場合に限って使用できます。</span><span class="sxs-lookup"><span data-stu-id="54bf1-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="54bf1-122">-debugSecurityZoneURL \<url></span><span class="sxs-lookup"><span data-stu-id="54bf1-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="54bf1-123">アプリケーションを、指定した [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] から展開されたものとしてデバッグする必要があることを PresentationHost.exe に指示するために、[!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] 値と共に使用します。</span><span class="sxs-lookup"><span data-stu-id="54bf1-123">Used with a [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span></span> <span data-ttu-id="54bf1-124">これは、展開ゾーンと起点サイトの両方を決定します。</span><span class="sxs-lookup"><span data-stu-id="54bf1-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="54bf1-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="54bf1-125">-embedding</span></span>|<span data-ttu-id="54bf1-126">OLE で必要になります。</span><span class="sxs-lookup"><span data-stu-id="54bf1-126">Required by OLE.</span></span> <span data-ttu-id="54bf1-127">`-event` パラメーターまたは `-debug` パラメーターを指定した場合、`-embedding` パラメーターは内部で設定されるため、指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="54bf1-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="54bf1-128">-event \<eventname></span><span class="sxs-lookup"><span data-stu-id="54bf1-128">-event \<eventname></span></span>|<span data-ttu-id="54bf1-129">PresentationHost.exe が初期化され、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] コンテンツをホストする準備ができた時点で、この名前のイベントを開き、シグナルを送信します。</span><span class="sxs-lookup"><span data-stu-id="54bf1-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="54bf1-130">PresentationHost.exe は、イベントを開く際にエラーが発生すると (そのイベントがまだ作成されていない場合など) 終了します。</span><span class="sxs-lookup"><span data-stu-id="54bf1-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="54bf1-131">-launchApplication \<url></span><span class="sxs-lookup"><span data-stu-id="54bf1-131">-launchApplication \<url></span></span>|<span data-ttu-id="54bf1-132">指定した URL から、スタンドアロンの [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="54bf1-132">Launches a standalone [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] application from the specified URL.</span></span> <span data-ttu-id="54bf1-133">.NET アプリケーションに関する [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] と WinINet のセキュリティ ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="54bf1-133">[!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="54bf1-134">シナリオ</span><span class="sxs-lookup"><span data-stu-id="54bf1-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="54bf1-135">シェル ハンドラー</span><span class="sxs-lookup"><span data-stu-id="54bf1-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="54bf1-136">MIME ハンドラー</span><span class="sxs-lookup"><span data-stu-id="54bf1-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="54bf1-137">Visual Studio によるデバッグ</span><span class="sxs-lookup"><span data-stu-id="54bf1-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="54bf1-138">Visual Studio によるゾーンでのデバッグ</span><span class="sxs-lookup"><span data-stu-id="54bf1-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="54bf1-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="54bf1-139">See also</span></span>

- [<span data-ttu-id="54bf1-140">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="54bf1-140">Security</span></span>](../security-wpf.md)
