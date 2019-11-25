---
title: カスタム拡張メソッドを実装して呼び出す方法 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
ms.openlocfilehash: f3d96c033380698ade37c49ecbfeed14f05d3e11
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73970893"
---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a><span data-ttu-id="d6d88-102">カスタム拡張メソッドを実装して呼び出す方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="d6d88-102">How to implement and call a custom extension method (C# Programming Guide)</span></span>
<span data-ttu-id="d6d88-103">このトピックでは、あらゆる .NET 型を対象に独自の拡張メソッドを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6d88-103">This topic shows how to implement your own extension methods for any .NET type.</span></span> <span data-ttu-id="d6d88-104">クライアント コードで拡張メソッドを使用するには、拡張メソッドが格納されている DLL への参照を追加し、拡張メソッドが定義されている名前空間を指定する [using](../../language-reference/keywords/using-directive.md) ディレクティブを追加します。</span><span class="sxs-lookup"><span data-stu-id="d6d88-104">Client code can use your extension methods by adding a reference to the DLL that contains them, and adding a [using](../../language-reference/keywords/using-directive.md) directive that specifies the namespace in which the extension methods are defined.</span></span>  
  
## <a name="to-define-and-call-the-extension-method"></a><span data-ttu-id="d6d88-105">拡張メソッドを定義して呼び出すには</span><span class="sxs-lookup"><span data-stu-id="d6d88-105">To define and call the extension method</span></span>  
  
1. <span data-ttu-id="d6d88-106">拡張メソッドを格納するための静的[クラス](./static-classes-and-static-class-members.md)を定義します。</span><span class="sxs-lookup"><span data-stu-id="d6d88-106">Define a static [class](./static-classes-and-static-class-members.md) to contain the extension method.</span></span>  
  
     <span data-ttu-id="d6d88-107">このクラスは、クライアント コードから参照できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6d88-107">The class must be visible to client code.</span></span> <span data-ttu-id="d6d88-108">アクセシビリティの規則の詳細については、「[アクセス修飾子](./access-modifiers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6d88-108">For more information about accessibility rules, see [Access Modifiers](./access-modifiers.md).</span></span>  
  
2. <span data-ttu-id="d6d88-109">拡張メソッドを静的メソッドとして実装します。メソッドの可視性は、包含クラスと同レベル以上を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6d88-109">Implement the extension method as a static method with at least the same visibility as the containing class.</span></span>  
  
3. <span data-ttu-id="d6d88-110">メソッドの最初のパラメーターでは、メソッドが操作する型を指定します。型名の前には [this](../../language-reference/keywords/this.md) 修飾子を付加します。</span><span class="sxs-lookup"><span data-stu-id="d6d88-110">The first parameter of the method specifies the type that the method operates on; it must be preceded with the [this](../../language-reference/keywords/this.md) modifier.</span></span>  
  
4. <span data-ttu-id="d6d88-111">呼び出し元のコードで、`using` ディレクティブを追加して、拡張メソッドのクラスを含む[名前空間](../../language-reference/keywords/namespace.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6d88-111">In the calling code, add a `using` directive to specify the [namespace](../../language-reference/keywords/namespace.md) that contains the extension method class.</span></span>  
  
5. <span data-ttu-id="d6d88-112">型のインスタンス メソッドと同じようにメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d6d88-112">Call the methods as if they were instance methods on the type.</span></span>  
  
     <span data-ttu-id="d6d88-113">呼び出し元のコードでは最初のパラメーターを指定しません。これは演算子を適用する型を表すものであり、コンパイラはオブジェクトの型を既に認識しているためです。</span><span class="sxs-lookup"><span data-stu-id="d6d88-113">Note that the first parameter is not specified by calling code because it represents the type on which the operator is being applied, and the compiler already knows the type of your object.</span></span> <span data-ttu-id="d6d88-114">指定する必要があるのは、2 番目から `n` 番目のパラメーターの引数だけです。</span><span class="sxs-lookup"><span data-stu-id="d6d88-114">You only have to provide arguments for parameters 2 through `n`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6d88-115">例</span><span class="sxs-lookup"><span data-stu-id="d6d88-115">Example</span></span>  
 <span data-ttu-id="d6d88-116">次の例では、`CustomExtensions.StringExtension` クラスの `WordCount` という名前の拡張メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="d6d88-116">The following example implements an extension method named `WordCount` in the `CustomExtensions.StringExtension` class.</span></span> <span data-ttu-id="d6d88-117">このメソッドは、最初のメソッド パラメーターとして指定された <xref:System.String> クラスを操作します。</span><span class="sxs-lookup"><span data-stu-id="d6d88-117">The method operates on the <xref:System.String> class, which is specified as the first method parameter.</span></span> <span data-ttu-id="d6d88-118">`CustomExtensions` 名前空間は、アプリケーション名前空間にインポートされ、メソッドは `Main` メソッド内で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d6d88-118">The `CustomExtensions` namespace is imported into the application namespace, and the method is called inside the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#1)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="d6d88-119">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="d6d88-119">.NET Framework Security</span></span>  
 <span data-ttu-id="d6d88-120">拡張メソッドには、固有のセキュリティ上の脆弱性はありません。</span><span class="sxs-lookup"><span data-stu-id="d6d88-120">Extension methods present no specific security vulnerabilities.</span></span> <span data-ttu-id="d6d88-121">名前の衝突の解決では、型自体で定義されているインスタンス メソッドまたは静的メソッドが常に優先されるため、型の既存のメソッドを偽装するために拡張メソッドが使用されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d6d88-121">They can never be used to impersonate existing methods on a type, because all name collisions are resolved in favor of the instance or static method defined by the type itself.</span></span> <span data-ttu-id="d6d88-122">拡張メソッドは、拡張されたクラスのプライベート データにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="d6d88-122">Extension methods cannot access any private data in the extended class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6d88-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6d88-123">See also</span></span>

- [<span data-ttu-id="d6d88-124">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d6d88-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d6d88-125">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="d6d88-125">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="d6d88-126">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="d6d88-126">LINQ (Language-Integrated Query)</span></span>](../../linq/linq-in-csharp.md)
- [<span data-ttu-id="d6d88-127">静的クラスと静的クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="d6d88-127">Static Classes and Static Class Members</span></span>](./static-classes-and-static-class-members.md)
- [<span data-ttu-id="d6d88-128">protected</span><span class="sxs-lookup"><span data-stu-id="d6d88-128">protected</span></span>](../../language-reference/keywords/protected.md)
- [<span data-ttu-id="d6d88-129">internal</span><span class="sxs-lookup"><span data-stu-id="d6d88-129">internal</span></span>](../../language-reference/keywords/internal.md)
- [<span data-ttu-id="d6d88-130">public</span><span class="sxs-lookup"><span data-stu-id="d6d88-130">public</span></span>](../../language-reference/keywords/public.md)
- [<span data-ttu-id="d6d88-131">this</span><span class="sxs-lookup"><span data-stu-id="d6d88-131">this</span></span>](../../language-reference/keywords/this.md)
- [<span data-ttu-id="d6d88-132">namespace</span><span class="sxs-lookup"><span data-stu-id="d6d88-132">namespace</span></span>](../../language-reference/keywords/namespace.md)
