---
title: Assembly
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
ms.openlocfilehash: 34d6b94f31336e3e99b8ca981a9c4899e5a3d912
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875520"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="b4835-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4835-102">Assembly (Visual Basic)</span></span>

<span data-ttu-id="b4835-103">ソース ファイルの先頭の属性がアセンブリ全体に適用されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="b4835-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4835-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="b4835-104">Remarks</span></span>  

 <span data-ttu-id="b4835-105">個々のプログラミング要素には、クラスやプロパティなどの多くの属性が関連しています。</span><span class="sxs-lookup"><span data-stu-id="b4835-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="b4835-106">そのような属性を適用するには、山かっこ (`< >`) 内の属性ブロックを宣言ステートメントに直接アタッチします。</span><span class="sxs-lookup"><span data-stu-id="b4835-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="b4835-107">属性が次の要素だけでなく、アセンブリ全体に関連する場合は、属性ブロックをソース ファイルの先頭に配置し、`Assembly` キーワードで属性を識別します。</span><span class="sxs-lookup"><span data-stu-id="b4835-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="b4835-108">それを現在のアセンブリ モジュールに適用する場合、[Module](module-keyword.md) キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="b4835-108">If it applies to the current assembly module, you use the [Module](module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="b4835-109">また、AssemblyInfo.vb ファイル内のアセンブリに属性を適用することもできます。この場合、メイン ソースコード ファイルで属性ブロックを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b4835-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4835-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4835-110">See also</span></span>

- [<span data-ttu-id="b4835-111">Module \<keyword></span><span class="sxs-lookup"><span data-stu-id="b4835-111">Module \<keyword></span></span>](module-keyword.md)
- [<span data-ttu-id="b4835-112">属性の概要</span><span class="sxs-lookup"><span data-stu-id="b4835-112">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
