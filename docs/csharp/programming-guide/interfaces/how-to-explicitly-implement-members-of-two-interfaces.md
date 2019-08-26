---
title: '方法: 2 つのインターフェイスのメンバーを明示的に実装する - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: 1d4dd0485be1d859e3e9594ab1558a907b8f1f7a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589199"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="0048b-102">方法: 2 つのインターフェイスのメンバーを明示的に実装する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="0048b-102">How to: Explicitly Implement Members of Two Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="0048b-103">明示的な[インターフェイス](../../language-reference/keywords/interface.md)実装では、プログラマは、メンバー名が同じ 2 つのインターフェイスを実装し、各インターフェイス メンバーに別の実装を与えることもできます。</span><span class="sxs-lookup"><span data-stu-id="0048b-103">Explicit [interface](../../language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="0048b-104">この例では、メートル法とヤード ポンド法の両方の単位で、ボックスのサイズを表示します。</span><span class="sxs-lookup"><span data-stu-id="0048b-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="0048b-105">Box [クラス](../../language-reference/keywords/class.md)では、異なる測定システムを表す IEnglishDimensions および IMetricDimensions という 2 つのインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="0048b-105">The Box [class](../../language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="0048b-106">両方のインターフェイスは Length および Width という同じメンバー名を持ちます。</span><span class="sxs-lookup"><span data-stu-id="0048b-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0048b-107">例</span><span class="sxs-lookup"><span data-stu-id="0048b-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a><span data-ttu-id="0048b-108">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="0048b-108">Robust Programming</span></span>  
 <span data-ttu-id="0048b-109">ヤード ポンド単位で既定の測定を行う場合は、通常どおり Length と Width のメソッドを実装し、IMetricDimensions インターフェイスから Length と Width のメソッドを明示的に実装します。</span><span class="sxs-lookup"><span data-stu-id="0048b-109">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 <span data-ttu-id="0048b-110">この場合、ヤード ポンド単位にはクラス インスタンスからアクセスでき、メートル単位にはインターフェイス インスタンスからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0048b-110">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="0048b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="0048b-111">See also</span></span>

- [<span data-ttu-id="0048b-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="0048b-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0048b-113">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="0048b-113">Classes and Structs</span></span>](../classes-and-structs/index.md)
- <span data-ttu-id="0048b-114">"[インターフェイス](./index.md)"</span><span class="sxs-lookup"><span data-stu-id="0048b-114">[Interfaces](./index.md)</span></span>
- [<span data-ttu-id="0048b-115">方法: インターフェイス メンバーを明示的に実装する</span><span class="sxs-lookup"><span data-stu-id="0048b-115">How to: Explicitly Implement Interface Members</span></span>](./how-to-explicitly-implement-interface-members.md)
