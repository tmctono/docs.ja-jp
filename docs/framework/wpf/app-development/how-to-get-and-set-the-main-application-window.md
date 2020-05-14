---
title: '方法: メイン アプリケーション ウィンドウを取得して設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows objects [WPF], setting
- setting windows objects [WPF]
- windows objects [WPF], getting
- getting windows objects [WPF]
ms.assetid: ec902bc4-4a59-46f5-8ec1-963b46789356
ms.openlocfilehash: 5894761c4b6258cbf90d369a722ffc5abca51885
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582556"
---
# <a name="how-to-get-and-set-the-main-application-window"></a><span data-ttu-id="1a587-102">方法: メイン アプリケーション ウィンドウを取得して設定する</span><span class="sxs-lookup"><span data-stu-id="1a587-102">How to: Get and Set the Main Application Window</span></span>
<span data-ttu-id="1a587-103">この例では、メイン アプリケーション ウィンドウを取得および設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1a587-103">This example shows how to get and set the main application window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a587-104">例</span><span class="sxs-lookup"><span data-stu-id="1a587-104">Example</span></span>  
 <span data-ttu-id="1a587-105">Windows Presentation Foundation (WPF) アプリケーション内で最初にインスタンス化された <xref:System.Windows.Window> は、<xref:System.Windows.Application> によってメイン アプリケーション ウィンドウとして自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1a587-105">The first <xref:System.Windows.Window> that is instantiated within a Windows Presentation Foundation (WPF) application is automatically set by <xref:System.Windows.Application> as the main application window.</span></span> <span data-ttu-id="1a587-106">通常、最初にインスタンス化される <xref:System.Windows.Window> は、スタートアップ URI (Uniform Resource Identifier) として指定されているウィンドウです (「<xref:System.Windows.Application.StartupUri%2A>」を参照)。</span><span class="sxs-lookup"><span data-stu-id="1a587-106">The first <xref:System.Windows.Window> to be instantiated will most likely be the window that is specified as the startup uniform resource identifier (URI) (see <xref:System.Windows.Application.StartupUri%2A>).</span></span>  
  
 <span data-ttu-id="1a587-107">最初の <xref:System.Windows.Window> は、コードを使用してインスタンス化することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a587-107">The first <xref:System.Windows.Window> could also be instantiated using code.</span></span> <span data-ttu-id="1a587-108">1 つの例として、次のように、アプリケーションの起動時にウィンドウを開くことがあります。</span><span class="sxs-lookup"><span data-stu-id="1a587-108">One example is opening a window during application startup, like the following:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 <span data-ttu-id="1a587-109">場合によっては、最初にインスタンス化される <xref:System.Windows.Window> が、実際にはメイン アプリケーション ウィンドウではないことがあります (スプラッシュ スクリーンなど)。</span><span class="sxs-lookup"><span data-stu-id="1a587-109">Sometimes, the first instantiated <xref:System.Windows.Window> is not actually the main application window e.g. a splash screen.</span></span> <span data-ttu-id="1a587-110">この場合は、次のように、マークアップを使用してメイン アプリケーション ウィンドウを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1a587-110">In this case, you can specify the main application window using markup, like the following:</span></span>  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 <span data-ttu-id="1a587-111">メイン ウィンドウが自動または手動のどちらで指定されるかにかかわらず、次のようなコードを使用して、<xref:System.Windows.Application.MainWindow%2A> からメイン ウィンドウを取得できます。</span><span class="sxs-lookup"><span data-stu-id="1a587-111">Whether the main window is specified automatically or manually, you can get the main window from <xref:System.Windows.Application.MainWindow%2A> using the following code, like the following:</span></span>  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
