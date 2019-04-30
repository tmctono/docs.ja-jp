---
title: '方法: Windows フォームの BindingNavigator コントロールを使用して DataSet を移動する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- datasets [Windows Forms], moving through
- BindingNavigator control [Windows Forms], moving through datasets
- examples [Windows Forms], BindingNavigator control
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
ms.openlocfilehash: d76c2e5882c9df94674294da00ba446dfbfd2b3a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012738"
---
# <a name="how-to-move-through-a-dataset-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="54df5-102">方法: Windows フォームの BindingNavigator コントロールを使用して DataSet を移動する</span><span class="sxs-lookup"><span data-stu-id="54df5-102">How to: Move Through a DataSet with the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="54df5-103">データ ドリブン アプリケーションを作成するときに、ユーザーにデータのコレクションを表示する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="54df5-103">As you build data-driven applications, you will often need to display collections of data to users.</span></span> <span data-ttu-id="54df5-104"><xref:System.Windows.Forms.BindingNavigator> コントロールは、<xref:System.Windows.Forms.BindingSource> コンポーネントと組み合わせて、コレクションを移動して項目を順番に表示する、便利で拡張可能なソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="54df5-104">The <xref:System.Windows.Forms.BindingNavigator> control, in conjunction with the <xref:System.Windows.Forms.BindingSource> component, provides a convenient and extensible solution for moving through a collection and displaying items sequentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54df5-105">例</span><span class="sxs-lookup"><span data-stu-id="54df5-105">Example</span></span>  
 <span data-ttu-id="54df5-106"><xref:System.Windows.Forms.BindingNavigator> コントロールを使用してデータ間を移動する方法を、次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="54df5-106">The following code example demonstrates how to use a <xref:System.Windows.Forms.BindingNavigator> control to move through data.</span></span> <span data-ttu-id="54df5-107">セットは <xref:System.Data.DataView> に含まれ、<xref:System.Windows.Forms.BindingSource> コンポーネントを持つ <xref:System.Windows.Forms.TextBox> コントロールにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="54df5-107">The set is contained in a <xref:System.Data.DataView>, which is bound to a <xref:System.Windows.Forms.TextBox> control with a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54df5-108">接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="54df5-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="54df5-109">データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="54df5-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="54df5-110">詳細については、「[接続情報の保護](../../data/adonet/protecting-connection-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54df5-110">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="54df5-111">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="54df5-111">Compiling the Code</span></span>  
 <span data-ttu-id="54df5-112">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="54df5-112">This example requires:</span></span>  
  
- <span data-ttu-id="54df5-113">System、System.Data、System.Drawing、System.Windows.Forms、および System.Xml アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="54df5-113">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="54df5-114">Visual Basic または Visual C# からこの例をビルドする方法については、[コマンド ラインからのビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)、または[csc.exe を使用したコマンド ラインからのビルド](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54df5-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="54df5-115">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="54df5-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54df5-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="54df5-116">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="54df5-117">BindingNavigator コントロール</span><span class="sxs-lookup"><span data-stu-id="54df5-117">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="54df5-118">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="54df5-118">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="54df5-119">方法: Windows フォーム コントロールを型にバインドします。</span><span class="sxs-lookup"><span data-stu-id="54df5-119">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
