---
title: '方法: Windows フォームでファイルに関連付けられているアイコンを抽出する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: d754dc5e8a57b3c4e2e5439bb2524a22d44813c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004043"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a><span data-ttu-id="32654-102">方法: Windows フォームでファイルに関連付けられているアイコンを抽出する</span><span class="sxs-lookup"><span data-stu-id="32654-102">How to: Extract the Icon Associated with a File in Windows Forms</span></span>
<span data-ttu-id="32654-103">多数のファイルには、関連付けられているファイルの種類のビジュアル表現を提供するアイコンが埋め込まれています。</span><span class="sxs-lookup"><span data-stu-id="32654-103">Many files have embedded icons that provide a visual representation of the associated file type.</span></span> <span data-ttu-id="32654-104">たとえば、Microsoft Word ドキュメントには、それらを Word 文書として識別するアイコンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="32654-104">For example, Microsoft Word documents contain an icon that identifies them as Word documents.</span></span> <span data-ttu-id="32654-105">リスト コントロールにテーブル コントロール ファイルを表示するときに各ファイル名の横にあるファイルの種類を表すアイコンを表示したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="32654-105">When displaying files in a list control or table control, you may want to display the icon representing the file type next to each file name.</span></span> <span data-ttu-id="32654-106">使用して簡単に行うことができます、<xref:System.Drawing.Icon.ExtractAssociatedIcon%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="32654-106">You can do this easily by using the <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32654-107">例</span><span class="sxs-lookup"><span data-stu-id="32654-107">Example</span></span>  
 <span data-ttu-id="32654-108">次のコード例は、ファイルに関連付けられたアイコンを抽出し、ファイル名と関連付けられているアイコンで表示する方法を示します、<xref:System.Windows.Forms.ListView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="32654-108">The following code example demonstrates how to extract the icon associated with a file and display the file name and its associated icon in a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="32654-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="32654-109">Compiling the Code</span></span>  
 <span data-ttu-id="32654-110">例をコンパイルするには。</span><span class="sxs-lookup"><span data-stu-id="32654-110">To compile the example:</span></span>  
  
- <span data-ttu-id="32654-111">Windows フォーム、および呼び出しに上記のコードを貼り付け、`ExtractAssociatedIconExample`フォームのコンス トラクターからメソッドまたは<xref:System.Windows.Forms.Form.Load>イベント処理メソッド。</span><span class="sxs-lookup"><span data-stu-id="32654-111">Paste the preceding code into a Windows Form, and call the `ExtractAssociatedIconExample` method from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     <span data-ttu-id="32654-112">フォームをインポートすることを確認する必要があります、<xref:System.IO>名前空間。</span><span class="sxs-lookup"><span data-stu-id="32654-112">You will need to make sure that your form imports the <xref:System.IO> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32654-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="32654-113">See also</span></span>

- [<span data-ttu-id="32654-114">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="32654-114">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="32654-115">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="32654-115">ListView Control</span></span>](../controls/listview-control-windows-forms.md)
