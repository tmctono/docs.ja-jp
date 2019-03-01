---
title: Visual Basic の Nothing と文字列
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: 873c4e40a0b12dd657d3294785e04dd9efc23956
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967985"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="37d1d-102">Visual Basic の Nothing と文字列</span><span class="sxs-lookup"><span data-stu-id="37d1d-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="37d1d-103">Visual Basic ランタイムと[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]評価`Nothing`が異なるとなる文字列。</span><span class="sxs-lookup"><span data-stu-id="37d1d-103">The Visual Basic runtime and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="37d1d-104">Visual Basic ランタイムと .NET Framework</span><span class="sxs-lookup"><span data-stu-id="37d1d-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="37d1d-105">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37d1d-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="37d1d-106">Visual Basic ランタイムは、通常は評価`Nothing`として空の文字列 ("")。</span><span class="sxs-lookup"><span data-stu-id="37d1d-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="37d1d-107">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]ただし、していないと、文字列操作を実行する試行が行われるたびに、例外をスローします`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="37d1d-107">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37d1d-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="37d1d-108">See also</span></span>
- [<span data-ttu-id="37d1d-109">Visual Basic の文字列の概要</span><span class="sxs-lookup"><span data-stu-id="37d1d-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
