---
title: '方法: 領域でヒット テストを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 136f15f1364fb2aed791b4a61d0f11411b055967
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778873"
---
# <a name="how-to-use-hit-testing-with-a-region"></a><span data-ttu-id="a7bae-102">方法: 領域でヒット テストを使用する</span><span class="sxs-lookup"><span data-stu-id="a7bae-102">How to: Use Hit Testing with a Region</span></span>
<span data-ttu-id="a7bae-103">ヒット テストの目的では、アイコンやボタンなどの特定のオブジェクトの上にカーソルがかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="a7bae-103">The purpose of hit testing is to determine whether the cursor is over a given object, such as an icon or a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7bae-104">例</span><span class="sxs-lookup"><span data-stu-id="a7bae-104">Example</span></span>  
 <span data-ttu-id="a7bae-105">次の例では、2 つの四角形領域の和集合を形成して十字型の領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="a7bae-105">The following example creates a plus-shaped region by forming the union of two rectangular regions.</span></span> <span data-ttu-id="a7bae-106">ある変数`point`最新のクリックの位置を保持します。</span><span class="sxs-lookup"><span data-stu-id="a7bae-106">Assume that the variable `point` holds the location of the most recent click.</span></span> <span data-ttu-id="a7bae-107">コードを調べますかどうか`point`十字型の領域にします。</span><span class="sxs-lookup"><span data-stu-id="a7bae-107">The code checks to see whether `point` is in the plus-shaped region.</span></span> <span data-ttu-id="a7bae-108">ポイントは、リージョン (ヒット) では場合、は、非透過の赤いブラシで領域が入力されます。</span><span class="sxs-lookup"><span data-stu-id="a7bae-108">If the point is in the region (a hit), the region is filled with an opaque red brush.</span></span> <span data-ttu-id="a7bae-109">それ以外の場合、領域は、半透明の赤いブラシで塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="a7bae-109">Otherwise, the region is filled with a semitransparent red brush.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a7bae-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="a7bae-110">Compiling the Code</span></span>  
 <span data-ttu-id="a7bae-111">前の例は、Windows フォームで使用するために設計されています。 また必要が<xref:System.Windows.Forms.PaintEventArgs> `e`、はのパラメーター<xref:System.Windows.Forms.PaintEventHandler>します。</span><span class="sxs-lookup"><span data-stu-id="a7bae-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7bae-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7bae-112">See also</span></span>

- <xref:System.Drawing.Region>
- [<span data-ttu-id="a7bae-113">GDI+ での領域</span><span class="sxs-lookup"><span data-stu-id="a7bae-113">Regions in GDI+</span></span>](regions-in-gdi.md)
- [<span data-ttu-id="a7bae-114">方法: クリッピング領域を使用します。</span><span class="sxs-lookup"><span data-stu-id="a7bae-114">How to: Use Clipping with a Region</span></span>](how-to-use-clipping-with-a-region.md)
