---
title: '方法: Windows フォームを印刷する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
ms.openlocfilehash: 85fb12028687578b76e0f16061deb9b9a4de70e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003978"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="18570-102">方法: Windows フォームを印刷する</span><span class="sxs-lookup"><span data-stu-id="18570-102">How to: Print a Windows Form</span></span>
<span data-ttu-id="18570-103">開発プロセスの一環として、通常は印刷する、Windows フォームのコピー。</span><span class="sxs-lookup"><span data-stu-id="18570-103">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="18570-104">次のコード例を使用して、現在のフォームのコピーを印刷する方法を示しています、<xref:System.Drawing.Graphics.CopyFromScreen%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="18570-104">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18570-105">例</span><span class="sxs-lookup"><span data-stu-id="18570-105">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="18570-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="18570-106">Compiling the Code</span></span>  
 <span data-ttu-id="18570-107">これは、完全なコード例を含む、`Main`メソッド。</span><span class="sxs-lookup"><span data-stu-id="18570-107">This is a complete code example that contains a `Main` method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="18570-108">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="18570-108">Robust Programming</span></span>  
 <span data-ttu-id="18570-109">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18570-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="18570-110">プリンターにアクセスするためのアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="18570-110">You do not have permission to access the printer.</span></span>  
  
- <span data-ttu-id="18570-111">プリンターをインストールすることはありません。</span><span class="sxs-lookup"><span data-stu-id="18570-111">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="18570-112">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="18570-112">.NET Framework Security</span></span>  
 <span data-ttu-id="18570-113">このコード例を実行するのには、コンピューターで使用するプリンターにアクセスするためのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="18570-113">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18570-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="18570-114">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="18570-115">方法: GDI + を使用したイメージをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="18570-115">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
- [<span data-ttu-id="18570-116">方法: Windows フォームでグラフィックスを印刷します。</span><span class="sxs-lookup"><span data-stu-id="18570-116">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)
