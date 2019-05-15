---
title: '方法: Firefox に対応した WPF プラグインがインストールされているかどうかを確認する'
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: 5ae2f39883c8edd7be912bfeb8326c14ca38704a
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592618"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="c7d4c-102">方法: Firefox に対応した WPF プラグインがインストールされているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="c7d4c-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>

<span data-ttu-id="c7d4c-103">Windows Presentation Foundation (WPF) の Firefox プラグインにより[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]Mozilla Firefox ブラウザーで実行するための XAML ファイルが失われるとします。</span><span class="sxs-lookup"><span data-stu-id="c7d4c-103">The Windows Presentation Foundation (WPF) plug-in for Firefox enables [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="c7d4c-104">このトピックでは、HTML と WPF の Firefox プラグインがインストールされているかどうかを判断する管理者が使用できる JavaScript で記述されたスクリプトを提供します。</span><span class="sxs-lookup"><span data-stu-id="c7d4c-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>

> [!NOTE]
> <span data-ttu-id="c7d4c-105">インストールの詳細については、配置、および、.NET Framework の検出について[開発者向けの .NET Framework のインストール](../../install/guide-for-developers.md)します。</span><span class="sxs-lookup"><span data-stu-id="c7d4c-105">For more information about installing, deploying, and detecting the .NET Framework, see [Install the .NET Framework for developers](../../install/guide-for-developers.md).</span></span>

## <a name="example"></a><span data-ttu-id="c7d4c-106">例</span><span class="sxs-lookup"><span data-stu-id="c7d4c-106">Example</span></span>

<span data-ttu-id="c7d4c-107">ときに、[!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]がインストールされている、クライアント コンピューターで構成されますプラグイン WPF firefox に対応します。</span><span class="sxs-lookup"><span data-stu-id="c7d4c-107">When the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="c7d4c-108">次のサンプル スクリプトでは、firefox に対応した WPF プラグインを確認し、適切な状態メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7d4c-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>

```html
<HTML>

  <HEAD>
    <TITLE>Test for the WPF plug-in for Firefox</TITLE>
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />
    <SCRIPT type="text/javascript">
    <!--
    function OnLoad()
    {

       // Check for the WPF plug-in for Firefox and report
       var msg = "The WPF plug-in for Firefox is ";
       var wpfPlugin = navigator.plugins["Windows Presentation Foundation"];
       if( wpfPlugin != null ) {
          document.writeln(msg + " installed.");
       }
       else {
          document.writeln(msg + " not installed. Please install or reinstall the .NET Framework 3.5.");
       }
    }
    -->
    </SCRIPT>
  </HEAD>

  <BODY onload="OnLoad()" />

</HTML>
```

<span data-ttu-id="c7d4c-109">Firefox に対応した WPF プラグインのチェックが成功した場合は、次のステータス メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7d4c-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is installed.`

<span data-ttu-id="c7d4c-110">それ以外の場合、次のステータス メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7d4c-110">Otherwise, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a><span data-ttu-id="c7d4c-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7d4c-111">See also</span></span>

- [<span data-ttu-id="c7d4c-112">.NET Framework 3.0 がインストールされているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="c7d4c-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [<span data-ttu-id="c7d4c-113">.NET Framework 3.5 がインストールされているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="c7d4c-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [<span data-ttu-id="c7d4c-114">WPF XAML ブラウザー アプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="c7d4c-114">WPF XAML Browser Applications Overview</span></span>](wpf-xaml-browser-applications-overview.md)
