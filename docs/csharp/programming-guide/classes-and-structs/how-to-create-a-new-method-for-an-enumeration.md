---
title: 列挙型対応の新しいメソッドを作成する方法 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 02af55c851392ce5dde4c83fd32d18b927950a3f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971032"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="a3ec0-102">列挙型対応の新しいメソッドを作成する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="a3ec0-102">How to create a new method for an enumeration (C# Programming Guide)</span></span>
<span data-ttu-id="a3ec0-103">拡張メソッドを使用して、特定の列挙型に固有の機能を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="a3ec0-103">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3ec0-104">例</span><span class="sxs-lookup"><span data-stu-id="a3ec0-104">Example</span></span>  
 <span data-ttu-id="a3ec0-105">次の例では、`Grades` 列挙型は学生が授業で受け取る成績評価を表わしています。</span><span class="sxs-lookup"><span data-stu-id="a3ec0-105">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="a3ec0-106">`Passing`という名前の拡張機能メソッドが`Grades`型に追加されていて、この型の各インスタンスが合格点を表しているかどうかを自ら "認識" できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="a3ec0-106">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 <span data-ttu-id="a3ec0-107">`Extensions` クラスには動的に更新される静的変数も含まれていて、拡張メソッドの戻り値はその変数の現在の値を反映していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a3ec0-107">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="a3ec0-108">背後では、拡張メソッドが自分が定義されている静的クラスに直接呼び出されることを、この例は示しています。</span><span class="sxs-lookup"><span data-stu-id="a3ec0-108">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3ec0-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3ec0-109">See also</span></span>

- [<span data-ttu-id="a3ec0-110">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="a3ec0-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a3ec0-111">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="a3ec0-111">Extension Methods</span></span>](./extension-methods.md)
