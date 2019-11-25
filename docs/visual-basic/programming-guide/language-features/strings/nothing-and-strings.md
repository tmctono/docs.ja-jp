---
title: テキストと文字列
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: dfc43748d0754f0a6a29763c42ab82d9937f89f8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344296"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="11d1e-102">Visual Basic の Nothing と文字列</span><span class="sxs-lookup"><span data-stu-id="11d1e-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="11d1e-103">The Visual Basic runtime and the .NET Framework evaluate `Nothing` differently when it comes to strings.</span><span class="sxs-lookup"><span data-stu-id="11d1e-103">The Visual Basic runtime and the .NET Framework evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="11d1e-104">Visual Basic Runtime and the .NET Framework</span><span class="sxs-lookup"><span data-stu-id="11d1e-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="11d1e-105">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="11d1e-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="11d1e-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span><span class="sxs-lookup"><span data-stu-id="11d1e-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="11d1e-107">The .NET Framework does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="11d1e-107">The .NET Framework does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11d1e-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="11d1e-108">See also</span></span>

- [<span data-ttu-id="11d1e-109">Visual Basic の文字列の概要</span><span class="sxs-lookup"><span data-stu-id="11d1e-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
