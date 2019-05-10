---
title: '方法: BindingSource と INotifyPropertyChanged の各インターフェイスを使用して変更通知を発生させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- change notifications [Windows Forms], raising
- BindingSource component [Windows Forms], and IPropertyChange
- data sources [Windows Forms], detecting changes
- examples [Windows Forms], BindingSource component
- change notifications
- INotifyPropertyChanged interface [Windows Forms], using with BindingSource
- BindingSource component [Windows Forms], examples
ms.assetid: 7fa2cf51-c09f-4375-adf0-e36c5617f099
ms.openlocfilehash: 93949f003a55cdf67c4ecde988d268728c75e081
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64614686"
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a><span data-ttu-id="d92f7-102">方法: BindingSource と INotifyPropertyChanged の各インターフェイスを使用して変更通知を発生させる</span><span class="sxs-lookup"><span data-stu-id="d92f7-102">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="d92f7-103">データ ソースに含まれる型が <xref:System.ComponentModel.INotifyPropertyChanged> インターフェイスを実装し、プロパティ値が変更されると <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> イベントを発生させる場合に、<xref:System.Windows.Forms.BindingSource> コンポーネントがデータ ソースの変更を自動的に検出します。</span><span class="sxs-lookup"><span data-stu-id="d92f7-103">The <xref:System.Windows.Forms.BindingSource> component will automatically detect changes in a data source when the type contained in the data source implements the <xref:System.ComponentModel.INotifyPropertyChanged> interface and raises <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> events when a property value is changed.</span></span> <span data-ttu-id="d92f7-104">これは、データ ソースの値が変わると、<xref:System.Windows.Forms.BindingSource> にバインドされるコントロールが自動的に更新されるため便利です。</span><span class="sxs-lookup"><span data-stu-id="d92f7-104">This is useful because controls bound to the <xref:System.Windows.Forms.BindingSource> will then automatically update as the data source values change.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d92f7-105">データ ソースが <xref:System.ComponentModel.INotifyPropertyChanged> を実装し、非同期操作を実行している場合は、バック グラウンド スレッド上のデータ ソースを変更しないようにします。</span><span class="sxs-lookup"><span data-stu-id="d92f7-105">If your data source implements <xref:System.ComponentModel.INotifyPropertyChanged> and you are performing asynchronous operations, you should not make changes to the data source on a background thread.</span></span> <span data-ttu-id="d92f7-106">代わりに、バック グラウンド スレッド上のデータを読み取り、UI スレッドでリストにデータをマージする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d92f7-106">Instead, you should read the data on a background thread and merge the data into a list on the UI thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d92f7-107">例</span><span class="sxs-lookup"><span data-stu-id="d92f7-107">Example</span></span>  
 <span data-ttu-id="d92f7-108">次のコード例は、<xref:System.ComponentModel.INotifyPropertyChanged> インターフェイスの簡単な実装を示します。</span><span class="sxs-lookup"><span data-stu-id="d92f7-108">The following code example demonstrates a simple implementation of the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="d92f7-109"><xref:System.Windows.Forms.BindingSource> が <xref:System.ComponentModel.INotifyPropertyChanged> 型の一覧にバインドされるときに、<xref:System.Windows.Forms.BindingSource> がバインドされたコントロールにデータ ソースの変更を自動的に渡す方法も示します。</span><span class="sxs-lookup"><span data-stu-id="d92f7-109">It also shows how the <xref:System.Windows.Forms.BindingSource> automatically passes a data source change to a bound control when the <xref:System.Windows.Forms.BindingSource> is bound to a list of the <xref:System.ComponentModel.INotifyPropertyChanged> type.</span></span>  
  
 <span data-ttu-id="d92f7-110">`CallerMemberName` 属性を使用する場合、`NotifyPropertyChanged` メソッドの呼び出しが、文字列引数としてプロパティ名を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d92f7-110">If you use the `CallerMemberName` attribute, calls to the `NotifyPropertyChanged` method don't have to specify the property name as a string argument.</span></span> <span data-ttu-id="d92f7-111">詳細については、次を参照してください。[呼び出し元情報 (C#)](../../../csharp/programming-guide/concepts/caller-information.md)または[呼び出し元情報 (Visual Basic)](../../../visual-basic/programming-guide/concepts/caller-information.md)します。</span><span class="sxs-lookup"><span data-stu-id="d92f7-111">For more information, see [Caller Information (C#)](../../../csharp/programming-guide/concepts/caller-information.md) or [Caller Information (Visual Basic)](../../../visual-basic/programming-guide/concepts/caller-information.md).</span></span>  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d92f7-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="d92f7-112">Compiling the Code</span></span>  
 <span data-ttu-id="d92f7-113">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d92f7-113">This example requires:</span></span>  
  
- <span data-ttu-id="d92f7-114">System、System.Data、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="d92f7-114">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="d92f7-115">コマンドラインからこの例を Visual Basic または Visual C# の構築方法の詳細については、[、コマンドラインからビルドする](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d92f7-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d92f7-116">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="d92f7-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span> <span data-ttu-id="d92f7-117">参照してください[方法。Visual Studio を使用して、完全な Windows フォームのコードの例をコンパイルして](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb129228(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="d92f7-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb129228(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d92f7-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d92f7-118">See also</span></span>

- <xref:System.ComponentModel.INotifyPropertyChanged>
- [<span data-ttu-id="d92f7-119">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d92f7-119">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="d92f7-120">方法: BindingSource ResetItem メソッドを使用して変更通知を発生させる</span><span class="sxs-lookup"><span data-stu-id="d92f7-120">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)
