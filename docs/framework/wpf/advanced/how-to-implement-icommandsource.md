---
title: '方法 : ICommandSource を実装する'
ms.date: 12/05/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 6c18e0b77ec53d9bd3e7ce610f2940effe603c88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174694"
---
# <a name="how-to-implement-icommandsource"></a><span data-ttu-id="17c85-102">方法 : ICommandSource を実装する</span><span class="sxs-lookup"><span data-stu-id="17c85-102">How to: Implement ICommandSource</span></span>

<span data-ttu-id="17c85-103">この例では、 を実装<xref:System.Windows.Input.ICommandSource>してコマンド ソースを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="17c85-103">This example shows how to create a command source by implementing <xref:System.Windows.Input.ICommandSource>.</span></span> <span data-ttu-id="17c85-104">コマンド ソースは、コマンドを呼び出す方法を知っているオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="17c85-104">A command source is an object that knows how to invoke a command.</span></span> <span data-ttu-id="17c85-105">この<xref:System.Windows.Input.ICommandSource>インターフェイスは、次の 3 つのメンバーを公開します。</span><span class="sxs-lookup"><span data-stu-id="17c85-105">The <xref:System.Windows.Input.ICommandSource> interface exposes three members:</span></span>

- <span data-ttu-id="17c85-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: 呼び出されるコマンド。</span><span class="sxs-lookup"><span data-stu-id="17c85-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: the command that will be invoked.</span></span>
- <span data-ttu-id="17c85-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: コマンド ソースからコマンドを処理するメソッドに渡されるユーザー定義データ型。</span><span class="sxs-lookup"><span data-stu-id="17c85-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: a user-defined data type which is passed from the command source to the method that handles the command.</span></span>
- <span data-ttu-id="17c85-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: コマンドが実行されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="17c85-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: the object that the command is being executed on.</span></span>

<span data-ttu-id="17c85-109">この例では、<xref:System.Windows.Controls.Slider>コントロールから継承し、インターフェイスを実装するクラスを作成します。 <xref:System.Windows.Input.ICommandSource></span><span class="sxs-lookup"><span data-stu-id="17c85-109">In this example, a class is created that inherits from the <xref:System.Windows.Controls.Slider> control and implements the  <xref:System.Windows.Input.ICommandSource> interface.</span></span>
  
## <a name="example"></a><span data-ttu-id="17c85-110">例</span><span class="sxs-lookup"><span data-stu-id="17c85-110">Example</span></span>

<span data-ttu-id="17c85-111"><xref:System.Windows.Input.ICommandSource>WPF には、 <xref:System.Windows.Controls.Button>、 <xref:System.Windows.Controls.MenuItem>、、および を実装する<xref:System.Windows.Documents.Hyperlink>クラスが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="17c85-111">WPF provides a number of classes which implement <xref:System.Windows.Input.ICommandSource>, such as <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, and <xref:System.Windows.Documents.Hyperlink>.</span></span> <span data-ttu-id="17c85-112">コマンド ソースは、コマンドを呼び出す方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="17c85-112">A command source defines how it invokes a command.</span></span> <span data-ttu-id="17c85-113">これらのクラスは、クリックされたときにコマンドを呼び出し、<xref:System.Windows.Input.ICommandSource.Command%2A>プロパティが設定されている場合にのみコマンド ソースになります。</span><span class="sxs-lookup"><span data-stu-id="17c85-113">These classes invoke a command when they're clicked and they only become a command source when their <xref:System.Windows.Input.ICommandSource.Command%2A> property is set.</span></span>

<span data-ttu-id="17c85-114">この例では、プロパティが変更されたときに、スライダーを動かすと、より正確にコマンドを<xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>呼び出します。</span><span class="sxs-lookup"><span data-stu-id="17c85-114">In this example, you'll invoke the command when the slider is moved, or more accurately, when the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property is changed.</span></span>

<span data-ttu-id="17c85-115">クラス定義は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="17c85-115">The following is the class definition:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

<span data-ttu-id="17c85-116">次の手順では、メンバーを<xref:System.Windows.Input.ICommandSource>実装します。</span><span class="sxs-lookup"><span data-stu-id="17c85-116">The next step is to implement the <xref:System.Windows.Input.ICommandSource> members.</span></span> <span data-ttu-id="17c85-117">この例では、プロパティはオブジェクトとして<xref:System.Windows.DependencyProperty>実装されています。</span><span class="sxs-lookup"><span data-stu-id="17c85-117">In this example, the properties are implemented as <xref:System.Windows.DependencyProperty> objects.</span></span> <span data-ttu-id="17c85-118">これにより、プロパティでデータ バインディングを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="17c85-118">This enables the properties to use data binding.</span></span> <span data-ttu-id="17c85-119">クラスの詳細については、「 <xref:System.Windows.DependencyProperty> [依存関係プロパティの概要](dependency-properties-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17c85-119">For more information about the <xref:System.Windows.DependencyProperty> class, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span> <span data-ttu-id="17c85-120">データ バインディングの詳細については、「 データ バインディングの[概要](../../../desktop-wpf/data/data-binding-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17c85-120">For more information about data binding, see the [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="17c85-121">ここでは、<xref:System.Windows.Input.ICommandSource.Command%2A>プロパティのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="17c85-121">Only the <xref:System.Windows.Input.ICommandSource.Command%2A> property is shown here.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
<span data-ttu-id="17c85-122">変更コールバックは<xref:System.Windows.DependencyProperty>次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="17c85-122">The following is the <xref:System.Windows.DependencyProperty> change callback:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

<span data-ttu-id="17c85-123">次の手順では、コマンド ソースに関連付けられているコマンドを追加および削除します。</span><span class="sxs-lookup"><span data-stu-id="17c85-123">The next step is to add and remove the command which is associated with the command source.</span></span> <span data-ttu-id="17c85-124">新<xref:System.Windows.Input.ICommandSource.Command%2A>しいコマンドが追加されたときに、プロパティを上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="17c85-124">The <xref:System.Windows.Input.ICommandSource.Command%2A> property cannot simply be overwritten when a new command is added, because the event handlers associated with the previous command, if there was one, must be removed first.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

<span data-ttu-id="17c85-125">次の手順では、ハンドラーのロジックを<xref:System.Windows.Input.ICommand.CanExecuteChanged>作成します。</span><span class="sxs-lookup"><span data-stu-id="17c85-125">The next step is to create logic for the <xref:System.Windows.Input.ICommand.CanExecuteChanged> handler.</span></span>

<span data-ttu-id="17c85-126">この<xref:System.Windows.Input.ICommand.CanExecuteChanged>イベントは、コマンドソースに、現在のコマンドターゲットで実行する機能が変更された可能性があることを通知します。</span><span class="sxs-lookup"><span data-stu-id="17c85-126">The <xref:System.Windows.Input.ICommand.CanExecuteChanged> event notifies the command source that the ability of the command to execute on the current command target may have changed.</span></span> <span data-ttu-id="17c85-127">コマンド ソースはこのイベントを受け取ると、通常は<xref:System.Windows.Input.ICommand.CanExecute%2A>コマンドのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="17c85-127">When a command source receives this event, it typically calls the <xref:System.Windows.Input.ICommand.CanExecute%2A> method on the command.</span></span> <span data-ttu-id="17c85-128">コマンドが現在のコマンド ターゲットで実行できない場合、通常、コマンド ソースは無効になります。</span><span class="sxs-lookup"><span data-stu-id="17c85-128">If the command cannot execute on the current command target, the command source will typically disable itself.</span></span> <span data-ttu-id="17c85-129">コマンドが現在のコマンド ターゲットで実行できる場合、通常、コマンド ソースは自身を有効にします。</span><span class="sxs-lookup"><span data-stu-id="17c85-129">If the command can execute on the current command target, the command source will typically enable itself.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

<span data-ttu-id="17c85-130">最後のステップは<xref:System.Windows.Input.ICommand.Execute%2A>メソッドです。</span><span class="sxs-lookup"><span data-stu-id="17c85-130">The last step is the <xref:System.Windows.Input.ICommand.Execute%2A> method.</span></span> <span data-ttu-id="17c85-131">コマンドが<xref:System.Windows.Input.RoutedCommand>の場合、メソッド<xref:System.Windows.Input.RoutedCommand><xref:System.Windows.Input.RoutedCommand.Execute%2A>が呼び出されます。それ以外の<xref:System.Windows.Input.ICommand><xref:System.Windows.Input.ICommand.Execute%2A>場合は、メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="17c85-131">If the command is a <xref:System.Windows.Input.RoutedCommand>, the <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> method is called; otherwise, the <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> method is called.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a><span data-ttu-id="17c85-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="17c85-132">See also</span></span>

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="17c85-133">コマンド実行の概要</span><span class="sxs-lookup"><span data-stu-id="17c85-133">Commanding Overview</span></span>](commanding-overview.md)
