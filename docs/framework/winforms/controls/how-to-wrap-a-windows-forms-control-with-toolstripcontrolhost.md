---
title: '方法: ToolStripControlHost を使用して Windows フォーム コントロールをラップする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStrip control [Windows Forms], wrapping controls
- toolbars [Windows Forms], wrapping controls
- ToolStrip control [Windows Forms], hosting controls
ms.assetid: e2ce4990-661d-4882-a116-8a9eb575dc84
ms.openlocfilehash: b90e47f9cd20d4f963f6223877cefc901f1c0667
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591573"
---
# <a name="how-to-wrap-a-windows-forms-control-with-toolstripcontrolhost"></a><span data-ttu-id="18dfa-102">方法: ToolStripControlHost を使用して Windows フォーム コントロールをラップする</span><span class="sxs-lookup"><span data-stu-id="18dfa-102">How to: Wrap a Windows Forms Control with ToolStripControlHost</span></span>
<span data-ttu-id="18dfa-103"><xref:System.Windows.Forms.ToolStripControlHost> は、<xref:System.Windows.Forms.ToolStripControlHost> コンストラクターを使用するか、<xref:System.Windows.Forms.ToolStripControlHost> 自身を拡張することによって、任意の Windows フォーム コントロールをホストできるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="18dfa-103"><xref:System.Windows.Forms.ToolStripControlHost> is designed to enable hosting of arbitrary Windows Forms controls by using the <xref:System.Windows.Forms.ToolStripControlHost> constructor or by extending <xref:System.Windows.Forms.ToolStripControlHost> itself.</span></span> <span data-ttu-id="18dfa-104">より簡単にコントロールをラップするには、<xref:System.Windows.Forms.ToolStripControlHost> を拡張し、頻繁に使用するコントロールのプロパティとメソッドを公開するプロパティとメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="18dfa-104">It is easier to wrap the control by extending <xref:System.Windows.Forms.ToolStripControlHost> and implementing properties and methods that expose frequently used properties and methods of the control.</span></span> <span data-ttu-id="18dfa-105">コントロールのイベントを <xref:System.Windows.Forms.ToolStripControlHost> レベルで公開することもできます。</span><span class="sxs-lookup"><span data-stu-id="18dfa-105">You can also expose events for the control at the <xref:System.Windows.Forms.ToolStripControlHost> level.</span></span>  
  
### <a name="to-host-a-control-in-a-toolstripcontrolhost-by-derivation"></a><span data-ttu-id="18dfa-106">派生により ToolStripControlHost でコントロールをホストするには</span><span class="sxs-lookup"><span data-stu-id="18dfa-106">To host a control in a ToolStripControlHost by derivation</span></span>  
  
1. <span data-ttu-id="18dfa-107"><xref:System.Windows.Forms.ToolStripControlHost> を拡張します。</span><span class="sxs-lookup"><span data-stu-id="18dfa-107">Extend <xref:System.Windows.Forms.ToolStripControlHost>.</span></span> <span data-ttu-id="18dfa-108">必要なコントロールを渡して基底クラスのコンストラクターを呼び出す既定のコンストラクターを実装します。</span><span class="sxs-lookup"><span data-stu-id="18dfa-108">Implement a default constructor that calls the base class constructor passing in the desired control.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#10)]  
  
2. <span data-ttu-id="18dfa-109">ラップされたコントロールと同じ型のプロパティを宣言し、プロパティのアクセサーに入れて正しい型のコントロールとして `Control` を返します。</span><span class="sxs-lookup"><span data-stu-id="18dfa-109">Declare a property of the same type as the wrapped control and return `Control` as the correct type of control in the property's accessor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#11](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#11)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#11)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#11)]  
  
3. <span data-ttu-id="18dfa-110">ラップされたコントロールで頻繁に使用される他のプロパティとメソッドを、拡張されたクラスのプロパティとメソッドを使用して公開します。</span><span class="sxs-lookup"><span data-stu-id="18dfa-110">Expose other frequently used properties and methods of the wrapped control with properties and methods in the extended class.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#12](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#12)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#12)]  
  
4. <span data-ttu-id="18dfa-111">必要に応じて、<xref:System.Windows.Forms.ToolStripControlHost.OnSubscribeControlEvents%2A> メソッドと <xref:System.Windows.Forms.ToolStripControlHost.OnUnsubscribeControlEvents%2A> メソッドをオーバーライドし、公開するコントロール イベントを追加します。</span><span class="sxs-lookup"><span data-stu-id="18dfa-111">Optionally, override the <xref:System.Windows.Forms.ToolStripControlHost.OnSubscribeControlEvents%2A>, and <xref:System.Windows.Forms.ToolStripControlHost.OnUnsubscribeControlEvents%2A> methods and add the control events you want to expose.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#16](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#16)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#16)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#16)]  
  
5. <span data-ttu-id="18dfa-112">公開するイベントに必要なラップを提供します。</span><span class="sxs-lookup"><span data-stu-id="18dfa-112">Provide the necessary wrapping for the events you want to expose.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#17](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#17)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#17)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#17)]  
  
## <a name="example"></a><span data-ttu-id="18dfa-113">例</span><span class="sxs-lookup"><span data-stu-id="18dfa-113">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ToolStripControlHost#13](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#13)]
 [!code-csharp[System.Windows.Forms.ToolStripControlHost#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#13)]
 [!code-vb[System.Windows.Forms.ToolStripControlHost#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#13)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="18dfa-114">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="18dfa-114">Compiling the Code</span></span>  
  
- <span data-ttu-id="18dfa-115">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="18dfa-115">This example requires:</span></span>  
  
- <span data-ttu-id="18dfa-116">System アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="18dfa-116">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="18dfa-117">コマンドラインからこの例を Visual Basic または Visual C# の構築方法の詳細については、[、コマンドラインからビルドする](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18dfa-117">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="18dfa-118">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="18dfa-118">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18dfa-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="18dfa-119">See also</span></span>

- <xref:System.Windows.Forms.ToolStripControlHost>
- [<span data-ttu-id="18dfa-120">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="18dfa-120">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="18dfa-121">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="18dfa-121">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="18dfa-122">ToolStrip テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="18dfa-122">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
