---
title: Module <keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: 6c4f24ad161302835be683e9d324ce32b16c4087
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867987"
---
# <a name="module-keyword-visual-basic"></a><span data-ttu-id="7e4aa-102">Module \<keyword> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e4aa-102">Module \<keyword> (Visual Basic)</span></span>

<span data-ttu-id="7e4aa-103">ソース ファイルの先頭の属性が現在のアセンブリ モジュールに適用されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-103">Specifies that an attribute at the beginning of a source file applies to the current assembly module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e4aa-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="7e4aa-104">Remarks</span></span>  

 <span data-ttu-id="7e4aa-105">個々のプログラミング要素には、クラスやプロパティなどの多くの属性が関連しています。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="7e4aa-106">そのような属性を適用するには、山かっこ (`< >`) 内の属性ブロックを宣言ステートメントに直接アタッチします。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="7e4aa-107">属性が次の要素だけでなく、現在のアセンブリ モジュールに関連する場合は、属性ブロックをソース ファイルの先頭に配置し、`Module` キーワードで属性を識別します。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-107">If an attribute pertains not only to the following element but to the current assembly module, you place the attribute block at the beginning of the source file and identify the attribute with the `Module` keyword.</span></span> <span data-ttu-id="7e4aa-108">それをアセンブリ全体に適用する場合は、[Assembly](assembly.md) キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-108">If it applies to the entire assembly, you use the [Assembly](assembly.md) keyword.</span></span>  
  
 <span data-ttu-id="7e4aa-109">`Module` 修飾子は、[Module ステートメント](../statements/module-statement.md)と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-109">The `Module` modifier is not the same as the [Module Statement](../statements/module-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e4aa-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e4aa-110">See also</span></span>

- [<span data-ttu-id="7e4aa-111">Assembly</span><span class="sxs-lookup"><span data-stu-id="7e4aa-111">Assembly</span></span>](assembly.md)
- [<span data-ttu-id="7e4aa-112">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="7e4aa-112">Module Statement</span></span>](../statements/module-statement.md)
- [<span data-ttu-id="7e4aa-113">属性の概要</span><span class="sxs-lookup"><span data-stu-id="7e4aa-113">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
