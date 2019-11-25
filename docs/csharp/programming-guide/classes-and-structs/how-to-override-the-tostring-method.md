---
title: ToString メソッドをオーバーライドする方法 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: 3d5b63609ea61764d4042d534c40d8032fb82841
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73970468"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="fbd68-102">ToString メソッドをオーバーライドする方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="fbd68-102">How to override the ToString method (C# Programming Guide)</span></span>

<span data-ttu-id="fbd68-103">C# では、すべてのクラスまたは構造体が、暗黙的に <xref:System.Object> クラスを継承します。</span><span class="sxs-lookup"><span data-stu-id="fbd68-103">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="fbd68-104">そのため、C# のすべてのオブジェクトが <xref:System.Object.ToString%2A> メソッドを取得し、そのオブジェクトの文字列表現を返します。</span><span class="sxs-lookup"><span data-stu-id="fbd68-104">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="fbd68-105">たとえば、`int` 型の変数はすべて `ToString` メソッドを持ち、次のようにその変数の内容を文字列として返すことができます。</span><span class="sxs-lookup"><span data-stu-id="fbd68-105">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#37)]  
  
 <span data-ttu-id="fbd68-106">カスタムのクラスまたは構造体を作成するときは、クライアント コードにカスタム型の情報を提供するため、<xref:System.Object.ToString%2A> メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbd68-106">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="fbd68-107">`ToString` メソッドで書式設定文字列やその他のカスタム形式を使用する方法については、「[型の書式設定](../../../standard/base-types/formatting-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbd68-107">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="fbd68-108">このメソッドを使用して提供する情報を決定するときは、作成したクラスまたは構造体が信頼関係のないコードによって使用されるかどうかを考慮します。</span><span class="sxs-lookup"><span data-stu-id="fbd68-108">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="fbd68-109">悪意があるコードで利用される可能性がある情報を提供しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="fbd68-109">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
<span data-ttu-id="fbd68-110">クラスまたは構造体内の `ToString` メソッドをオーバーライドする手順</span><span class="sxs-lookup"><span data-stu-id="fbd68-110">To override the `ToString` method in your class or struct:</span></span>
  
1. <span data-ttu-id="fbd68-111">次の修飾子および戻り値の値を指定して、`ToString` メソッドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="fbd68-111">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2. <span data-ttu-id="fbd68-112">文字列を返すように、メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="fbd68-112">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="fbd68-113">次の例では、特定のクラス インスタンスに固有のデータに加えて、クラス名も返されます。</span><span class="sxs-lookup"><span data-stu-id="fbd68-113">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     [!code-csharp[csProgGuideInheritance#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#36)]  
  
     <span data-ttu-id="fbd68-114">`ToString` メソッドをテストする方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="fbd68-114">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="fbd68-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbd68-115">See also</span></span>

- <xref:System.IFormattable>
- [<span data-ttu-id="fbd68-116">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="fbd68-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fbd68-117">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="fbd68-117">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="fbd68-118">文字列</span><span class="sxs-lookup"><span data-stu-id="fbd68-118">Strings</span></span>](../strings/index.md)
- [<span data-ttu-id="fbd68-119">string</span><span class="sxs-lookup"><span data-stu-id="fbd68-119">string</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="fbd68-120">override</span><span class="sxs-lookup"><span data-stu-id="fbd68-120">override</span></span>](../../language-reference/keywords/override.md)
- [<span data-ttu-id="fbd68-121">virtual</span><span class="sxs-lookup"><span data-stu-id="fbd68-121">virtual</span></span>](../../language-reference/keywords/virtual.md)
- [<span data-ttu-id="fbd68-122">型の書式設定</span><span class="sxs-lookup"><span data-stu-id="fbd68-122">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
