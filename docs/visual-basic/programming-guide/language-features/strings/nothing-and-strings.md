---
title: Visual Basic の Nothing と文字列
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: f5c1ea8cc0728b25e8e874963967aed504e466d7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591348"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="2af0b-102">Visual Basic の Nothing と文字列</span><span class="sxs-lookup"><span data-stu-id="2af0b-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="2af0b-103">Visual Basic ランタイムと .NET Framework の評価`Nothing`が異なるとなる文字列。</span><span class="sxs-lookup"><span data-stu-id="2af0b-103">The Visual Basic runtime and the .NET Framework evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="2af0b-104">Visual Basic ランタイムと .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2af0b-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="2af0b-105">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2af0b-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="2af0b-106">Visual Basic ランタイムは、通常は評価`Nothing`として空の文字列 ("")。</span><span class="sxs-lookup"><span data-stu-id="2af0b-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="2af0b-107">.NET Framework ただし、していないと、文字列操作を実行する試行が行われるたびに、例外をスローします`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="2af0b-107">The .NET Framework does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2af0b-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="2af0b-108">See also</span></span>

- [<span data-ttu-id="2af0b-109">Visual Basic の文字列の概要</span><span class="sxs-lookup"><span data-stu-id="2af0b-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
