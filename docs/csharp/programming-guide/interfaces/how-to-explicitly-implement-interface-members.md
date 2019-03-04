---
title: '方法: インターフェイス メンバーを明示的に実装する - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: d5630065ae1fbfceca9ce3b5180664bba3a104a6
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "57201873"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="a1ddf-102">方法: インターフェイス メンバーを明示的に実装する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="a1ddf-102">How to: Explicitly Implement Interface Members (C# Programming Guide)</span></span>
<span data-ttu-id="a1ddf-103">この例では[インターフェイス](../../../csharp/language-reference/keywords/interface.md)、`IDimensions`、およびクラス `Box` を宣言します。これは、インターフェイス メンバーの `getLength` と `getWidth` を明示的に実装します。</span><span class="sxs-lookup"><span data-stu-id="a1ddf-103">This example declares an [interface](../../../csharp/language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `getLength` and `getWidth`.</span></span> <span data-ttu-id="a1ddf-104">メンバーには、インターフェイス インスタンス `dimensions` を介してアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a1ddf-104">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1ddf-105">例</span><span class="sxs-lookup"><span data-stu-id="a1ddf-105">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="a1ddf-106">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="a1ddf-106">Robust Programming</span></span>  
  
-   <span data-ttu-id="a1ddf-107">`Main` メソッドでは、次の行はコメントアウトされます。これらの行でコンパイル エラーが発生するためです。</span><span class="sxs-lookup"><span data-stu-id="a1ddf-107">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="a1ddf-108">明示的に実装されるインターフェイス メンバーに、[クラス](../../../csharp/language-reference/keywords/class.md) インスタンスからアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a1ddf-108">An interface member that is explicitly implemented cannot be accessed from a [class](../../../csharp/language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
-   <span data-ttu-id="a1ddf-109">`Main` メソッドの以下の行では、メソッドがインターフェイスのインスタンスから呼び出されるため、ボックスのサイズを正常に出力できます。</span><span class="sxs-lookup"><span data-stu-id="a1ddf-109">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a><span data-ttu-id="a1ddf-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1ddf-110">See also</span></span>

- [<span data-ttu-id="a1ddf-111">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="a1ddf-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a1ddf-112">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="a1ddf-112">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="a1ddf-113">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1ddf-113">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
- [<span data-ttu-id="a1ddf-114">方法: 2 つのインターフェイスのメンバーを明示的に実装する</span><span class="sxs-lookup"><span data-stu-id="a1ddf-114">How to: Explicitly Implement Members of Two Interfaces</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)
