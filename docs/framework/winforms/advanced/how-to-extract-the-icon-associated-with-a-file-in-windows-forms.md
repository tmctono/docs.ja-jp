---
title: '方法: ファイルに関連付けられているアイコンを抽出する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: 28769144b0e1c631a31c3c541747a6215f861d0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742541"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a><span data-ttu-id="6b16f-102">方法 : Windows フォームでファイルに関連付けられているアイコンを抽出する</span><span class="sxs-lookup"><span data-stu-id="6b16f-102">How to: Extract the Icon Associated with a File in Windows Forms</span></span>
<span data-ttu-id="6b16f-103">多くのファイルには、関連付けられたファイルの種類を視覚的に表現するアイコンが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="6b16f-103">Many files have embedded icons that provide a visual representation of the associated file type.</span></span> <span data-ttu-id="6b16f-104">たとえば、Microsoft Word 文書には、それらを Word 文書として識別するアイコンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b16f-104">For example, Microsoft Word documents contain an icon that identifies them as Word documents.</span></span> <span data-ttu-id="6b16f-105">リストコントロールまたはテーブルコントロールにファイルを表示する場合、各ファイル名の横にあるファイルの種類を表すアイコンを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="6b16f-105">When displaying files in a list control or table control, you may want to display the icon representing the file type next to each file name.</span></span> <span data-ttu-id="6b16f-106">これは、<xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> メソッドを使用して簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6b16f-106">You can do this easily by using the <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b16f-107">使用例</span><span class="sxs-lookup"><span data-stu-id="6b16f-107">Example</span></span>  
 <span data-ttu-id="6b16f-108">次のコード例は、ファイルに関連付けられたアイコンを抽出し、ファイル名とそれに関連付けられているアイコンを <xref:System.Windows.Forms.ListView> コントロールに表示する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b16f-108">The following code example demonstrates how to extract the icon associated with a file and display the file name and its associated icon in a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6b16f-109">コードのコンパイル方法</span><span class="sxs-lookup"><span data-stu-id="6b16f-109">Compiling the Code</span></span>  
 <span data-ttu-id="6b16f-110">この例をコンパイルするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="6b16f-110">To compile the example:</span></span>  
  
- <span data-ttu-id="6b16f-111">前のコードを Windows フォームに貼り付け、フォームのコンストラクターまたは <xref:System.Windows.Forms.Form.Load> イベント処理メソッドから `ExtractAssociatedIconExample` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6b16f-111">Paste the preceding code into a Windows Form, and call the `ExtractAssociatedIconExample` method from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     <span data-ttu-id="6b16f-112">フォームが <xref:System.IO> 名前空間をインポートすることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b16f-112">You will need to make sure that your form imports the <xref:System.IO> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b16f-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b16f-113">See also</span></span>

- [<span data-ttu-id="6b16f-114">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="6b16f-114">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="6b16f-115">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="6b16f-115">ListView Control</span></span>](../controls/listview-control-windows-forms.md)
