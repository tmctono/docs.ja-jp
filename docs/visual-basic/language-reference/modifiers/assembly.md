---
title: Assembly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
ms.openlocfilehash: 819fa9cf1bd25e9426fb1e75925a269fcf7a71cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801994"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="bc54f-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc54f-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="bc54f-103">ソース ファイルの先頭にある属性がアセンブリ全体に適用されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="bc54f-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc54f-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="bc54f-104">Remarks</span></span>  
 <span data-ttu-id="bc54f-105">多くの属性は、クラスやプロパティなどの個別のプログラミング要素に適用されます。</span><span class="sxs-lookup"><span data-stu-id="bc54f-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="bc54f-106">山かっこ内で、属性ブロックを接続することによってこのような属性を適用する (`< >`)、宣言ステートメントに直接します。</span><span class="sxs-lookup"><span data-stu-id="bc54f-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="bc54f-107">属性ブロックをソース ファイルの先頭に配置しを持つ属性を特定するだけでなく、次の要素をアセンブリ全体に属性が関係している場合、`Assembly`キーワード。</span><span class="sxs-lookup"><span data-stu-id="bc54f-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="bc54f-108">現在のアセンブリ モジュールに適用される場合に使用する、[モジュール](../../../visual-basic/language-reference/modifiers/module-keyword.md)キーワード。</span><span class="sxs-lookup"><span data-stu-id="bc54f-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="bc54f-109">適用することも、属性、AssemblyInfo.vb ファイルでアセンブリに、メインのソース コード ファイルで属性ブロックを使用するがあるない場合。</span><span class="sxs-lookup"><span data-stu-id="bc54f-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc54f-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc54f-110">See also</span></span>

- [<span data-ttu-id="bc54f-111">Module \<キーワード></span><span class="sxs-lookup"><span data-stu-id="bc54f-111">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [<span data-ttu-id="bc54f-112">属性の概要</span><span class="sxs-lookup"><span data-stu-id="bc54f-112">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
