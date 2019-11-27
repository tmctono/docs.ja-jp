---
title: アセンブリ
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
ms.openlocfilehash: 1385919a1205a60104125fff1bdd24f409a091df
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351648"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="c6e21-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6e21-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="c6e21-103">ソースファイルの先頭の属性がアセンブリ全体に適用されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="c6e21-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6e21-104">コメント</span><span class="sxs-lookup"><span data-stu-id="c6e21-104">Remarks</span></span>  
 <span data-ttu-id="c6e21-105">クラスやプロパティなど、多くの属性が個々のプログラミング要素に関連しています。</span><span class="sxs-lookup"><span data-stu-id="c6e21-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="c6e21-106">このような属性を適用するには、山かっこ (`< >`) 内で属性ブロックを宣言ステートメントに直接アタッチします。</span><span class="sxs-lookup"><span data-stu-id="c6e21-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="c6e21-107">属性が次の要素だけでなく、アセンブリ全体に関連する場合は、属性ブロックをソースファイルの先頭に配置し、`Assembly` キーワードを使用して属性を識別します。</span><span class="sxs-lookup"><span data-stu-id="c6e21-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="c6e21-108">現在のアセンブリモジュールに適用される場合は、 [module](../../../visual-basic/language-reference/modifiers/module-keyword.md)キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6e21-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="c6e21-109">また、AssemblyInfo ファイル内のアセンブリに属性を適用することもできます。この場合、メインのソースコードファイルで属性ブロックを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c6e21-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e21-110">参照</span><span class="sxs-lookup"><span data-stu-id="c6e21-110">See also</span></span>

- [<span data-ttu-id="c6e21-111">Module \<キーワード></span><span class="sxs-lookup"><span data-stu-id="c6e21-111">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [<span data-ttu-id="c6e21-112">属性の概要</span><span class="sxs-lookup"><span data-stu-id="c6e21-112">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
