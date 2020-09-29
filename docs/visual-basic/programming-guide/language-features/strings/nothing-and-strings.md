---
title: テキストと文字列
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: d4c7ee6d13334617a80abb845af52bf388a12797
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072523"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="beb9c-102">Visual Basic の Nothing と文字列</span><span class="sxs-lookup"><span data-stu-id="beb9c-102">Nothing and Strings in Visual Basic</span></span>

<span data-ttu-id="beb9c-103">Visual Basic ランタイムと .NET Framework では、文字列に関する `Nothing` の評価が異なります。</span><span class="sxs-lookup"><span data-stu-id="beb9c-103">The Visual Basic runtime and the .NET Framework evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="beb9c-104">Visual Basic ランタイムと .NET Framework</span><span class="sxs-lookup"><span data-stu-id="beb9c-104">Visual Basic Runtime and the .NET Framework</span></span>  

 <span data-ttu-id="beb9c-105">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="beb9c-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="beb9c-106">通常、Visual Basic ランタイムでは、`Nothing` が空の文字列 ("") として評価されます。</span><span class="sxs-lookup"><span data-stu-id="beb9c-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="beb9c-107">ただし、.NET Framework では実行されず、`Nothing` に対して文字列操作を実行しようとするたびに例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="beb9c-107">The .NET Framework does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beb9c-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="beb9c-108">See also</span></span>

- [<span data-ttu-id="beb9c-109">Visual Basic の文字列の概要</span><span class="sxs-lookup"><span data-stu-id="beb9c-109">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
