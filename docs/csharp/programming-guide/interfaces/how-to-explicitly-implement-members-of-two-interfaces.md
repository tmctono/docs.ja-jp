---
title: 2 つのインターフェイスのメンバーを明示的に実装する方法 - C# プログラミング ガイド
description: この C# の例では、メンバー名が同じ 2 つのインターフェイスを明示的に実装し、各インターフェイス メンバーに個別の実装を与える方法について説明します。
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: d60ec43f734d5e8bfa7f467874440bd3514877fe
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303063"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="fa904-103">2 つのインターフェイスのメンバーを明示的に実装する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="fa904-103">How to explicitly implement members of two interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="fa904-104">明示的な[インターフェイス](../../language-reference/keywords/interface.md)実装では、プログラマは、メンバー名が同じ 2 つのインターフェイスを実装し、各インターフェイス メンバーに別の実装を与えることもできます。</span><span class="sxs-lookup"><span data-stu-id="fa904-104">Explicit [interface](../../language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="fa904-105">この例では、メートル法とヤード ポンド法の両方の単位で、ボックスのサイズを表示します。</span><span class="sxs-lookup"><span data-stu-id="fa904-105">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="fa904-106">Box [クラス](../../language-reference/keywords/class.md)では、異なる測定システムを表す IEnglishDimensions および IMetricDimensions という 2 つのインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="fa904-106">The Box [class](../../language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="fa904-107">両方のインターフェイスは Length および Width という同じメンバー名を持ちます。</span><span class="sxs-lookup"><span data-stu-id="fa904-107">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa904-108">例</span><span class="sxs-lookup"><span data-stu-id="fa904-108">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a><span data-ttu-id="fa904-109">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="fa904-109">Robust Programming</span></span>  
 <span data-ttu-id="fa904-110">ヤード ポンド単位で既定の測定を行う場合は、通常どおり Length と Width のメソッドを実装し、IMetricDimensions インターフェイスから Length と Width のメソッドを明示的に実装します。</span><span class="sxs-lookup"><span data-stu-id="fa904-110">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 <span data-ttu-id="fa904-111">この場合、ヤード ポンド単位にはクラス インスタンスからアクセスでき、メートル単位にはインターフェイス インスタンスからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fa904-111">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="fa904-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa904-112">See also</span></span>

- [<span data-ttu-id="fa904-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="fa904-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fa904-114">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="fa904-114">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="fa904-115">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa904-115">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="fa904-116">インターフェイス メンバーを明示的に実装する方法</span><span class="sxs-lookup"><span data-stu-id="fa904-116">How to explicitly implement interface members</span></span>](./how-to-explicitly-implement-interface-members.md)
