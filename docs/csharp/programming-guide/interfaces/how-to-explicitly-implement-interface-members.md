---
title: インターフェイス メンバーを明示的に実装する方法 - C# プログラミング ガイド
description: この C# の例では、インターフェイス メンバーを明示的に実装する方法について説明します。 メンバーには、インターフェイス インスタンスを介してアクセスします。
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: 35b512ff6cbee1dd942f5b3476db660481808297
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303076"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="89dd8-104">インターフェイス メンバーを明示的に実装する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="89dd8-104">How to explicitly implement interface members (C# Programming Guide)</span></span>
<span data-ttu-id="89dd8-105">この例では[インターフェイス](../../language-reference/keywords/interface.md)、`IDimensions`、およびクラス `Box` を宣言します。これは、インターフェイス メンバーの `GetLength` と `GetWidth` を明示的に実装します。</span><span class="sxs-lookup"><span data-stu-id="89dd8-105">This example declares an [interface](../../language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `GetLength` and `GetWidth`.</span></span> <span data-ttu-id="89dd8-106">メンバーには、インターフェイス インスタンス `dimensions` を介してアクセスします。</span><span class="sxs-lookup"><span data-stu-id="89dd8-106">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89dd8-107">例</span><span class="sxs-lookup"><span data-stu-id="89dd8-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="89dd8-108">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="89dd8-108">Robust Programming</span></span>  
  
- <span data-ttu-id="89dd8-109">`Main` メソッドでは、次の行はコメントアウトされます。これらの行でコンパイル エラーが発生するためです。</span><span class="sxs-lookup"><span data-stu-id="89dd8-109">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="89dd8-110">明示的に実装されるインターフェイス メンバーに、[クラス](../../language-reference/keywords/class.md) インスタンスからアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="89dd8-110">An interface member that is explicitly implemented cannot be accessed from a [class](../../language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- <span data-ttu-id="89dd8-111">`Main` メソッドの以下の行では、メソッドがインターフェイスのインスタンスから呼び出されるため、ボックスのサイズを正常に出力できます。</span><span class="sxs-lookup"><span data-stu-id="89dd8-111">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a><span data-ttu-id="89dd8-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="89dd8-112">See also</span></span>

- [<span data-ttu-id="89dd8-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="89dd8-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="89dd8-114">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="89dd8-114">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="89dd8-115">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="89dd8-115">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="89dd8-116">2 つのインターフェイスのメンバーを明示的に実装する方法</span><span class="sxs-lookup"><span data-stu-id="89dd8-116">How to explicitly implement members of two interfaces</span></span>](./how-to-explicitly-implement-members-of-two-interfaces.md)
