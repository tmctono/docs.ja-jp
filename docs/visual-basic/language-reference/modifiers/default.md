---
title: 既定値
ms.date: 07/20/2015
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
ms.openlocfilehash: ad4c9528f208cc2c31f07b0506d1b049a7568c86
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351577"
---
# <a name="default-visual-basic"></a><span data-ttu-id="04db4-102">Default (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04db4-102">Default (Visual Basic)</span></span>
<span data-ttu-id="04db4-103">クラス、構造体、またはインターフェイスの既定のプロパティとしてプロパティを識別します。</span><span class="sxs-lookup"><span data-stu-id="04db4-103">Identifies a property as the default property of its class, structure, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04db4-104">コメント</span><span class="sxs-lookup"><span data-stu-id="04db4-104">Remarks</span></span>  
 <span data-ttu-id="04db4-105">クラス、構造体、またはインターフェイスは、そのプロパティが少なくとも1つのパラメーターを受け取ることができる限り、そのプロパティを*既定のプロパティ*として1つだけ指定できます。</span><span class="sxs-lookup"><span data-stu-id="04db4-105">A class, structure, or interface can designate at most one of its properties as the *default property*, provided that property takes at least one parameter.</span></span> <span data-ttu-id="04db4-106">コードがメンバーを指定せずにクラスまたは構造体への参照を作成した場合、Visual Basic は既定のプロパティへの参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="04db4-106">If code makes a reference to a class or structure without specifying a member, Visual Basic resolves that reference to the default property.</span></span>  
  
 <span data-ttu-id="04db4-107">既定のプロパティを使用すると、ソースコード文字が小さくなることがありますが、コードの読み取りが困難になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="04db4-107">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="04db4-108">呼び出し元のコードがクラスまたは構造体に精通していない場合、クラスまたは構造体の名前への参照を作成するときに、その参照がクラスまたは構造体自体、または既定のプロパティにアクセスするかどうかを特定できません。</span><span class="sxs-lookup"><span data-stu-id="04db4-108">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="04db4-109">これにより、コンパイラエラーまたは微妙な実行時のロジックエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="04db4-109">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="04db4-110">[Option Strict ステートメント](../../../visual-basic/language-reference/statements/option-strict-statement.md)を常に使用してコンパイラの型チェックを `On`に設定することにより、既定のプロパティエラーが発生する可能性を多少減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="04db4-110">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="04db4-111">定義済みのクラスまたは構造体をコード内で使用する予定の場合は、既定のプロパティがあるかどうかを判断し、存在する場合はその名前を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04db4-111">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="04db4-112">これらの欠点があるため、既定のプロパティを定義しないことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="04db4-112">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="04db4-113">コードを読みやすくするために、常にすべてのプロパティを明示的に参照することも検討する必要があります。既定のプロパティも同様です。</span><span class="sxs-lookup"><span data-stu-id="04db4-113">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
 <span data-ttu-id="04db4-114">このコンテキストでは、`Default` 修飾子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="04db4-114">The `Default` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="04db4-115">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="04db4-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="04db4-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="04db4-116">See also</span></span>

- [<span data-ttu-id="04db4-117">方法: Visual Basic で既定のプロパティを宣言して呼び出す</span><span class="sxs-lookup"><span data-stu-id="04db4-117">How to: Declare and Call a Default Property in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="04db4-118">キーワード</span><span class="sxs-lookup"><span data-stu-id="04db4-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
