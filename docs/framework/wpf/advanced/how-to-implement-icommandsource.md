---
title: '方法 : ICommandSource を実装する'
ms.date: 12/05/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 755377d25a2deb48aa9da86d4182075e30763530
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345098"
---
# <a name="how-to-implement-icommandsource"></a><span data-ttu-id="b7922-102">方法 : ICommandSource を実装する</span><span class="sxs-lookup"><span data-stu-id="b7922-102">How to: Implement ICommandSource</span></span>

<span data-ttu-id="b7922-103">この例では、<xref:System.Windows.Input.ICommandSource>を実装してコマンドソースを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b7922-103">This example shows how to create a command source by implementing <xref:System.Windows.Input.ICommandSource>.</span></span> <span data-ttu-id="b7922-104">コマンドソースは、コマンドの呼び出し方法を認識しているオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="b7922-104">A command source is an object that knows how to invoke a command.</span></span> <span data-ttu-id="b7922-105"><xref:System.Windows.Input.ICommandSource> インターフェイスは、次の3つのメンバーを公開します。</span><span class="sxs-lookup"><span data-stu-id="b7922-105">The <xref:System.Windows.Input.ICommandSource> interface exposes three members:</span></span>

- <span data-ttu-id="b7922-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: 呼び出されるコマンド。</span><span class="sxs-lookup"><span data-stu-id="b7922-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: the command that will be invoked.</span></span>
- <span data-ttu-id="b7922-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: コマンドソースからコマンドを処理するメソッドに渡されるユーザー定義データ型。</span><span class="sxs-lookup"><span data-stu-id="b7922-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: a user-defined data type which is passed from the command source to the method that handles the command.</span></span>
- <span data-ttu-id="b7922-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: コマンドが実行されているオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b7922-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: the object that the command is being executed on.</span></span>

<span data-ttu-id="b7922-109">この例では、<xref:System.Windows.Controls.Slider> コントロールから継承し、<xref:System.Windows.Input.ICommandSource> インターフェイスを実装するクラスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b7922-109">In this example, a class is created that inherits from the <xref:System.Windows.Controls.Slider> control and implements the  <xref:System.Windows.Input.ICommandSource> interface.</span></span>
  
## <a name="example"></a><span data-ttu-id="b7922-110">使用例</span><span class="sxs-lookup"><span data-stu-id="b7922-110">Example</span></span>

<span data-ttu-id="b7922-111">WPF には、<xref:System.Windows.Controls.Button>、<xref:System.Windows.Controls.MenuItem>、<xref:System.Windows.Documents.Hyperlink>などの <xref:System.Windows.Input.ICommandSource>を実装するクラスが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="b7922-111">WPF provides a number of classes which implement <xref:System.Windows.Input.ICommandSource>, such as <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, and <xref:System.Windows.Documents.Hyperlink>.</span></span> <span data-ttu-id="b7922-112">コマンドソースは、コマンドの呼び出し方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="b7922-112">A command source defines how it invokes a command.</span></span> <span data-ttu-id="b7922-113">これらのクラスは、クリックされたときにコマンドを呼び出し、<xref:System.Windows.Input.ICommandSource.Command%2A> プロパティが設定されている場合にのみコマンドソースになります。</span><span class="sxs-lookup"><span data-stu-id="b7922-113">These classes invoke a command when they're clicked and they only become a command source when their <xref:System.Windows.Input.ICommandSource.Command%2A> property is set.</span></span>

<span data-ttu-id="b7922-114">この例では、<xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> プロパティが変更されたときに、スライダーが移動されたとき、またはより正確にコマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b7922-114">In this example, you'll invoke the command when the slider is moved, or more accurately, when the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property is changed.</span></span>

<span data-ttu-id="b7922-115">クラス定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b7922-115">The following is the class definition:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

<span data-ttu-id="b7922-116">次の手順では、<xref:System.Windows.Input.ICommandSource> メンバーを実装します。</span><span class="sxs-lookup"><span data-stu-id="b7922-116">The next step is to implement the <xref:System.Windows.Input.ICommandSource> members.</span></span> <span data-ttu-id="b7922-117">この例では、プロパティは <xref:System.Windows.DependencyProperty> オブジェクトとして実装されています。</span><span class="sxs-lookup"><span data-stu-id="b7922-117">In this example, the properties are implemented as <xref:System.Windows.DependencyProperty> objects.</span></span> <span data-ttu-id="b7922-118">これにより、プロパティでデータバインディングを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b7922-118">This enables the properties to use data binding.</span></span> <span data-ttu-id="b7922-119"><xref:System.Windows.DependencyProperty> クラスの詳細については、「[依存関係プロパティの概要](dependency-properties-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7922-119">For more information about the <xref:System.Windows.DependencyProperty> class, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span> <span data-ttu-id="b7922-120">データバインディングの詳細については、「[データバインディングの概要](../../../desktop-wpf/data/data-binding-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7922-120">For more information about data binding, see the [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="b7922-121">ここでは、<xref:System.Windows.Input.ICommandSource.Command%2A> プロパティのみを示しています。</span><span class="sxs-lookup"><span data-stu-id="b7922-121">Only the <xref:System.Windows.Input.ICommandSource.Command%2A> property is shown here.</span></span>
 
[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
<span data-ttu-id="b7922-122">次に、<xref:System.Windows.DependencyProperty> の変更コールバックを示します。</span><span class="sxs-lookup"><span data-stu-id="b7922-122">The following is the <xref:System.Windows.DependencyProperty> change callback:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

<span data-ttu-id="b7922-123">次の手順では、コマンドソースに関連付けられているコマンドを追加および削除します。</span><span class="sxs-lookup"><span data-stu-id="b7922-123">The next step is to add and remove the command which is associated with the command source.</span></span> <span data-ttu-id="b7922-124">前のコマンドに関連付けられているイベントハンドラー (存在する場合) を最初に削除する必要があるため、新しいコマンドが追加されたときには、<xref:System.Windows.Input.ICommandSource.Command%2A> プロパティを単に上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b7922-124">The <xref:System.Windows.Input.ICommandSource.Command%2A> property cannot simply be overwritten when a new command is added, because the event handlers associated with the previous command, if there was one, must be removed first.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

<span data-ttu-id="b7922-125">次の手順では、<xref:System.Windows.Input.ICommand.CanExecuteChanged> ハンドラーのロジックを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7922-125">The next step is to create logic for the <xref:System.Windows.Input.ICommand.CanExecuteChanged> handler.</span></span>

<span data-ttu-id="b7922-126"><xref:System.Windows.Input.ICommand.CanExecuteChanged> イベントは、現在のコマンドターゲットで実行するコマンドの機能が変更された可能性があることをコマンドソースに通知します。</span><span class="sxs-lookup"><span data-stu-id="b7922-126">The <xref:System.Windows.Input.ICommand.CanExecuteChanged> event notifies the command source that the ability of the command to execute on the current command target may have changed.</span></span> <span data-ttu-id="b7922-127">コマンドソースがこのイベントを受け取ると、通常はコマンドの <xref:System.Windows.Input.ICommand.CanExecute%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b7922-127">When a command source receives this event, it typically calls the <xref:System.Windows.Input.ICommand.CanExecute%2A> method on the command.</span></span> <span data-ttu-id="b7922-128">コマンドが現在のコマンドターゲットで実行できない場合、コマンドソースは通常、それ自体を無効にします。</span><span class="sxs-lookup"><span data-stu-id="b7922-128">If the command cannot execute on the current command target, the command source will typically disable itself.</span></span> <span data-ttu-id="b7922-129">コマンドが現在のコマンドターゲットで実行できる場合、コマンドソースは通常、それ自体を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b7922-129">If the command can execute on the current command target, the command source will typically enable itself.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

<span data-ttu-id="b7922-130">最後の手順は <xref:System.Windows.Input.ICommand.Execute%2A> メソッドです。</span><span class="sxs-lookup"><span data-stu-id="b7922-130">The last step is the <xref:System.Windows.Input.ICommand.Execute%2A> method.</span></span> <span data-ttu-id="b7922-131">コマンドが <xref:System.Windows.Input.RoutedCommand>の場合、<xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> メソッドが呼び出されます。それ以外の場合は、<xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b7922-131">If the command is a <xref:System.Windows.Input.RoutedCommand>, the <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> method is called; otherwise, the <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> method is called.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a><span data-ttu-id="b7922-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7922-132">See also</span></span>

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="b7922-133">コマンド実行の概要</span><span class="sxs-lookup"><span data-stu-id="b7922-133">Commanding Overview</span></span>](commanding-overview.md)
