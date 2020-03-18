---
title: 2 つのインターフェイスのメンバーを明示的に実装する方法 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: c7adc08f62a7f8a14b8e10f8b5ecdd6e37db811d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75701239"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="e6038-102">2 つのインターフェイスのメンバーを明示的に実装する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="e6038-102">How to explicitly implement members of two interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="e6038-103">明示的な[インターフェイス](../../language-reference/keywords/interface.md)実装では、プログラマは、メンバー名が同じ 2 つのインターフェイスを実装し、各インターフェイス メンバーに別の実装を与えることもできます。</span><span class="sxs-lookup"><span data-stu-id="e6038-103">Explicit [interface](../../language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="e6038-104">この例では、メートル法とヤード ポンド法の両方の単位で、ボックスのサイズを表示します。</span><span class="sxs-lookup"><span data-stu-id="e6038-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="e6038-105">Box [クラス](../../language-reference/keywords/class.md)では、異なる測定システムを表す IEnglishDimensions および IMetricDimensions という 2 つのインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="e6038-105">The Box [class](../../language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="e6038-106">両方のインターフェイスは Length および Width という同じメンバー名を持ちます。</span><span class="sxs-lookup"><span data-stu-id="e6038-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6038-107">例</span><span class="sxs-lookup"><span data-stu-id="e6038-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a><span data-ttu-id="e6038-108">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="e6038-108">Robust Programming</span></span>  
 <span data-ttu-id="e6038-109">ヤード ポンド単位で既定の測定を行う場合は、通常どおり Length と Width のメソッドを実装し、IMetricDimensions インターフェイスから Length と Width のメソッドを明示的に実装します。</span><span class="sxs-lookup"><span data-stu-id="e6038-109">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 <span data-ttu-id="e6038-110">この場合、ヤード ポンド単位にはクラス インスタンスからアクセスでき、メートル単位にはインターフェイス インスタンスからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e6038-110">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="e6038-111">参照</span><span class="sxs-lookup"><span data-stu-id="e6038-111">See also</span></span>

- [<span data-ttu-id="e6038-112">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="e6038-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e6038-113">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="e6038-113">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="e6038-114">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6038-114">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="e6038-115">インターフェイス メンバーを明示的に実装する方法</span><span class="sxs-lookup"><span data-stu-id="e6038-115">How to explicitly implement interface members</span></span>](./how-to-explicitly-implement-interface-members.md)
