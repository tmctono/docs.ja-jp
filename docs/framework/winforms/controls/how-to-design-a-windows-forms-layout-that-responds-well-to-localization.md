---
title: '方法: ローカリゼーションに対応した Windows フォーム レイアウトをデザインする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: c1aa62413e1c9cc29507b7b0ed5cbf1c5fcea26a
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928566"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a><span data-ttu-id="9508c-102">方法: ローカリゼーションに対応した Windows フォーム レイアウトをデザインする</span><span class="sxs-lookup"><span data-stu-id="9508c-102">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>
<span data-ttu-id="9508c-103">ローカライズが可能なフォームを作成すると、各国市場向けの開発期間が大幅に短縮されます。</span><span class="sxs-lookup"><span data-stu-id="9508c-103">Creating forms that are ready to be localized greatly speeds development for international markets.</span></span> <span data-ttu-id="9508c-104"><xref:System.Windows.Forms.TableLayoutPanel> コントロールを使用すると、<xref:System.Windows.Forms.Control.Text%2A> プロパティ値の変更によってコントロールのサイズが変更された際に、これに適切に応答するレイアウトを実装できます</span><span class="sxs-lookup"><span data-stu-id="9508c-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to implement layouts that respond gracefully as controls resize due to changes in their <xref:System.Windows.Forms.Control.Text%2A> property values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9508c-105">例</span><span class="sxs-lookup"><span data-stu-id="9508c-105">Example</span></span>  
 <span data-ttu-id="9508c-106">このフォームでは、表示される文字列値を他の言語に翻訳するときに、均等に調整されるレイアウトを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9508c-106">This form demonstrates how to create a layout that proportionally adjusts when you translate displayed string values into other languages.</span></span> <span data-ttu-id="9508c-107">この翻訳プロセスのことを "*ローカリゼーション*" といいます。</span><span class="sxs-lookup"><span data-stu-id="9508c-107">This process of translation is called *localization*.</span></span> <span data-ttu-id="9508c-108">詳細については、「[ローカリゼーション](../../../standard/globalization-localization/localization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9508c-108">For more information, see [Localization](../../../standard/globalization-localization/localization.md).</span></span>  
  
 <span data-ttu-id="9508c-109">Visual Studio では、このタスクに対する広範なサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9508c-109">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="9508c-110">[「チュートリアル:ローカライズ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))の比率を調整するレイアウトを作成する。</span><span class="sxs-lookup"><span data-stu-id="9508c-110">See also [Walkthrough: Creating a Layout That Adjusts Proportion for Localization](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
## <a name="additional-resources"></a><span data-ttu-id="9508c-111">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="9508c-111">Additional resources</span></span>

1. [<span data-ttu-id="9508c-112">方法: TableLayoutPanel コントロールでのコントロールの配置と伸縮</span><span class="sxs-lookup"><span data-stu-id="9508c-112">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2. [<span data-ttu-id="9508c-113">チュートリアル: FlowLayoutPanel を使用した Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="9508c-113">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  

3. [<span data-ttu-id="9508c-114">方法: TableLayoutPanel コントロールの行と列をスパンする</span><span class="sxs-lookup"><span data-stu-id="9508c-114">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
4. [<span data-ttu-id="9508c-115">方法: TableLayoutPanel コントロールの列と行を編集する</span><span class="sxs-lookup"><span data-stu-id="9508c-115">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
5. [<span data-ttu-id="9508c-116">チュートリアル: Windows フォームコントロールでのスマートタグを使用した一般的なタスクの実行</span><span class="sxs-lookup"><span data-stu-id="9508c-116">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)  
  
6. [<span data-ttu-id="9508c-117">チュートリアル: TableLayoutPanel を使用した Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="9508c-117">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  

7. [<span data-ttu-id="9508c-118">チュートリアル: パディング、余白、AutoSize プロパティを使用して Windows フォームコントロールをレイアウトする</span><span class="sxs-lookup"><span data-stu-id="9508c-118">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)  
  
8. <span data-ttu-id="9508c-119">[方法: AutoSize と TableLayoutPanel コントロールを使用した Windows フォームでのローカライズのサポート](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9508c-119">[How to: Support Localization on Windows Forms Using AutoSize and the TableLayoutPanel Control](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))</span></span>  
  
9. <span data-ttu-id="9508c-120">[チュートリアル: データ入力用のサイズ変更可能な Windows フォームの作成](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9508c-120">[Walkthrough: Creating a Resizable Windows Form for Data Entry](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9508c-121">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="9508c-121">Compiling the Code</span></span>  
 <span data-ttu-id="9508c-122">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9508c-122">This example requires:</span></span>  
  
- <span data-ttu-id="9508c-123">System、System.Data、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="9508c-123">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9508c-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="9508c-124">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- [<span data-ttu-id="9508c-125">ローカリゼーション</span><span class="sxs-lookup"><span data-stu-id="9508c-125">Localization</span></span>](../../../standard/globalization-localization/localization.md)
