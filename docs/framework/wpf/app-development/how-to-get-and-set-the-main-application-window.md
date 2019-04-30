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
ms.openlocfilehash: ea8333aa82f1159afb438215940ee1e7c2605e96
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947798"
---
# <a name="how-to-get-and-set-the-main-application-window"></a><span data-ttu-id="caf8a-102">方法: メイン アプリケーション ウィンドウを取得して設定する</span><span class="sxs-lookup"><span data-stu-id="caf8a-102">How to: Get and Set the Main Application Window</span></span>
<span data-ttu-id="caf8a-103">この例では、取得し、アプリケーションのメイン ウィンドウを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="caf8a-103">This example shows how to get and set the main application window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="caf8a-104">例</span><span class="sxs-lookup"><span data-stu-id="caf8a-104">Example</span></span>  
 <span data-ttu-id="caf8a-105">最初の<xref:System.Windows.Window>内で、Windows Presentation Foundation (WPF) アプリケーションはによって自動的に設定がインスタンス化される<xref:System.Windows.Application>メイン アプリケーション ウィンドウとして。</span><span class="sxs-lookup"><span data-stu-id="caf8a-105">The first <xref:System.Windows.Window> that is instantiated within a Windows Presentation Foundation (WPF) application is automatically set by <xref:System.Windows.Application> as the main application window.</span></span> <span data-ttu-id="caf8a-106">最初の<xref:System.Windows.Window>インスタンス化は、通常、スタートアップとして指定されているウィンドウをある[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)](を参照してください<xref:System.Windows.Application.StartupUri%2A>)。</span><span class="sxs-lookup"><span data-stu-id="caf8a-106">The first <xref:System.Windows.Window> to be instantiated will most likely be the window that is specified as the startup [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (see <xref:System.Windows.Application.StartupUri%2A>).</span></span>  
  
 <span data-ttu-id="caf8a-107">最初の<xref:System.Windows.Window>コードを使用してインスタンス可能性があります。</span><span class="sxs-lookup"><span data-stu-id="caf8a-107">The first <xref:System.Windows.Window> could also be instantiated using code.</span></span> <span data-ttu-id="caf8a-108">1 つの例では、次のように、アプリケーションの起動時にウィンドウを開いては。</span><span class="sxs-lookup"><span data-stu-id="caf8a-108">One example is opening a window during application startup, like the following:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 <span data-ttu-id="caf8a-109">場合によっては、1 つ目のインスタンス化<xref:System.Windows.Window>が実際には、アプリケーションのメイン ウィンドウなど、スプラッシュ スクリーン。</span><span class="sxs-lookup"><span data-stu-id="caf8a-109">Sometimes, the first instantiated <xref:System.Windows.Window> is not actually the main application window e.g. a splash screen.</span></span> <span data-ttu-id="caf8a-110">この場合は、次のようなマークアップを使用して、メイン アプリケーション ウィンドウを指定できます。</span><span class="sxs-lookup"><span data-stu-id="caf8a-110">In this case, you can specify the main application window using markup, like the following:</span></span>  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 <span data-ttu-id="caf8a-111">メイン ウィンドウが自動または手動で指定されているかどうか、メイン ウィンドウから取得できます<xref:System.Windows.Application.MainWindow%2A>次のように、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="caf8a-111">Whether the main window is specified automatically or manually, you can get the main window from <xref:System.Windows.Application.MainWindow%2A> using the following code, like the following:</span></span>  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
