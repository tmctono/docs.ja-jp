---
title: '方法: RoutedCommand を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- RoutedCommand class [WPF], creating
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
ms.openlocfilehash: 4119a762bd0db63108d08a9db9367e367adb6b58
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372088"
---
# <a name="how-to-create-a-routedcommand"></a><span data-ttu-id="9da00-102">方法: RoutedCommand を作成する</span><span class="sxs-lookup"><span data-stu-id="9da00-102">How to: Create a RoutedCommand</span></span>
<span data-ttu-id="9da00-103">カスタムを作成する方法を示します<xref:System.Windows.Input.RoutedCommand>を作成して、カスタム コマンドを実装する方法と、<xref:System.Windows.Input.ExecutedRoutedEventHandler>と<xref:System.Windows.Input.CanExecuteRoutedEventHandler>にアタッチし、<xref:System.Windows.Input.CommandBinding>します。</span><span class="sxs-lookup"><span data-stu-id="9da00-103">This example shows how to create a custom <xref:System.Windows.Input.RoutedCommand> and how to implement the custom command by creating a <xref:System.Windows.Input.ExecutedRoutedEventHandler> and a <xref:System.Windows.Input.CanExecuteRoutedEventHandler> and attaching them to a <xref:System.Windows.Input.CommandBinding>.</span></span>  <span data-ttu-id="9da00-104">コマンド実行の詳細については、、[コマンド実行の概要](commanding-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9da00-104">For more information on commanding, see the [Commanding Overview](commanding-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9da00-105">例</span><span class="sxs-lookup"><span data-stu-id="9da00-105">Example</span></span>  
 <span data-ttu-id="9da00-106">最初の手順で作成、<xref:System.Windows.Input.RoutedCommand>コマンドを定義して、インスタンス化することができます。</span><span class="sxs-lookup"><span data-stu-id="9da00-106">The first step in creating a <xref:System.Windows.Input.RoutedCommand> is defining the command and instantiating it.</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 <span data-ttu-id="9da00-107">アプリケーションで、コマンドを使用するには、コマンドの内容を定義するイベント ハンドラーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da00-107">In order to use the command in an application, event handlers which define what the command does must be created</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 <span data-ttu-id="9da00-108">次に、<xref:System.Windows.Input.CommandBinding>作成コマンドにイベント ハンドラーを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="9da00-108">Next, a  <xref:System.Windows.Input.CommandBinding> is created which associates the command with the event handlers.</span></span> <span data-ttu-id="9da00-109"><xref:System.Windows.Input.CommandBinding>特定のオブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9da00-109">The <xref:System.Windows.Input.CommandBinding> is created on a specific object.</span></span>  <span data-ttu-id="9da00-110">このオブジェクトのスコープを定義する、<xref:System.Windows.Input.CommandBinding>要素ツリー</span><span class="sxs-lookup"><span data-stu-id="9da00-110">This object defines the scope of the <xref:System.Windows.Input.CommandBinding> in the element tree</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 <span data-ttu-id="9da00-111">最後の手順では、コマンドを呼び出すことです。</span><span class="sxs-lookup"><span data-stu-id="9da00-111">The final step is invoking the command.</span></span>  <span data-ttu-id="9da00-112">コマンドを呼び出す方法の 1 つは、それを関連付ける、<xref:System.Windows.Input.ICommandSource>など、<xref:System.Windows.Controls.Button>します。</span><span class="sxs-lookup"><span data-stu-id="9da00-112">One way to invoke a command is to associate it with a <xref:System.Windows.Input.ICommandSource>, such as a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 <span data-ttu-id="9da00-113">ボタンがクリックされたときに、 <xref:System.Windows.Input.RoutedCommand.Execute%2A> 、カスタム<xref:System.Windows.Input.RoutedCommand>が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9da00-113">When the Button is clicked, the <xref:System.Windows.Input.RoutedCommand.Execute%2A> method on the custom <xref:System.Windows.Input.RoutedCommand> is called.</span></span>  <span data-ttu-id="9da00-114"><xref:System.Windows.Input.RoutedCommand>発生させる、<xref:System.Windows.Input.CommandManager.PreviewExecuted>と<xref:System.Windows.Input.CommandManager.Executed>ルーティング イベント。</span><span class="sxs-lookup"><span data-stu-id="9da00-114">The <xref:System.Windows.Input.RoutedCommand> raises the <xref:System.Windows.Input.CommandManager.PreviewExecuted> and <xref:System.Windows.Input.CommandManager.Executed> routed events.</span></span>  <span data-ttu-id="9da00-115">これらのイベントを探して、要素ツリーの走査、<xref:System.Windows.Input.CommandBinding>この特定のコマンド。</span><span class="sxs-lookup"><span data-stu-id="9da00-115">These events traverse the element tree looking for a <xref:System.Windows.Input.CommandBinding> for this particular command.</span></span>  <span data-ttu-id="9da00-116">場合、<xref:System.Windows.Input.CommandBinding>が見つかると、<xref:System.Windows.Input.ExecutedRoutedEventHandler>に関連付けられている<xref:System.Windows.Input.CommandBinding>が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9da00-116">If a <xref:System.Windows.Input.CommandBinding> is found, the <xref:System.Windows.Input.ExecutedRoutedEventHandler> associated with <xref:System.Windows.Input.CommandBinding> is called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9da00-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="9da00-117">See also</span></span>
- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="9da00-118">コマンド実行の概要</span><span class="sxs-lookup"><span data-stu-id="9da00-118">Commanding Overview</span></span>](commanding-overview.md)
