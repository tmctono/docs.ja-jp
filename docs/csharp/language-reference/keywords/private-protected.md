---
title: private protected - C# リファレンス
ms.custom: seodec18
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 35b7c6c4e271b7772968ad63926fe1e66b10a6fa
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633342"
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="db4c6-102">private protected (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="db4c6-102">private protected (C# Reference)</span></span>

<span data-ttu-id="db4c6-103">キーワード組み合わせ `private protected` はメンバー アクセス修飾子です。</span><span class="sxs-lookup"><span data-stu-id="db4c6-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="db4c6-104">private protected メンバーには、包含クラスから派生した型からアクセスできますが、その包含アセンブリ内に限られます。</span><span class="sxs-lookup"><span data-stu-id="db4c6-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="db4c6-105">`private protected` と他のアクセス修飾子の比較については、「[アクセシビリティ レベル](accessibility-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db4c6-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="db4c6-106">`private protected` アクセス修飾子は、C# バージョン 7.2 以降で有効です。</span><span class="sxs-lookup"><span data-stu-id="db4c6-106">The `private protected` access modifier is valid in C# version 7.2 and later.</span></span>

## <a name="example"></a><span data-ttu-id="db4c6-107">例</span><span class="sxs-lookup"><span data-stu-id="db4c6-107">Example</span></span>

<span data-ttu-id="db4c6-108">基底クラスの private protected メンバーには、変数の静的な型が派生クラス型の場合にのみ、その包含アセンブリで派生型からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="db4c6-108">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="db4c6-109">たとえば、次のコード セグメントを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="db4c6-109">For example, consider the following code segment:</span></span>  

```csharp
// Assembly1.cs  
// Compile with: /target:library  
public class BaseClass
{
    private protected int myValue = 0;
}

public class DerivedClass1 : BaseClass
{
    void Access()
    {
        BaseClass baseObject = new BaseClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 5;  

        // OK, accessed through the current derived class instance
        myValue = 5;
    }
}
```

```csharp
// Assembly2.cs  
// Compile with: /reference:Assembly1.dll  
class DerivedClass2 : BaseClass
{
    void Access()
    {
        // Error CS0122, because myValue can only be
        // accessed by types in Assembly1
        // myValue = 10;
    }
}
```

<span data-ttu-id="db4c6-110">この例には、2 つのファイル (`Assembly1.cs` と `Assembly2.cs`) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="db4c6-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="db4c6-111">最初のファイルには public 基底クラスである `BaseClass` とそれから派生した型である `DerivedClass1` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="db4c6-111">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="db4c6-112">`BaseClass` は private protected メンバー `myValue` を持っています。`DerivedClass1` はこれに 2 通りのアクセスを試行します。</span><span class="sxs-lookup"><span data-stu-id="db4c6-112">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="db4c6-113">最初に `BaseClass` のインスタンス経由で `myValue` にアクセスしようとするとエラーが出ます。</span><span class="sxs-lookup"><span data-stu-id="db4c6-113">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="db4c6-114">ただし、`DerivedClass1` で継承されたメンバーとして使用してみると成功します。</span><span class="sxs-lookup"><span data-stu-id="db4c6-114">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="db4c6-115">2 番目のファイルでは、`DerivedClass2` の継承されたメンバーとして `myValue` にアクセスしようとしてエラーを出します。これには Assembly1 の派生型のみがアクセスできるためです。</span><span class="sxs-lookup"><span data-stu-id="db4c6-115">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span>

<span data-ttu-id="db4c6-116">構造体は継承できないため、構造体メンバーは `private protected` になりません。</span><span class="sxs-lookup"><span data-stu-id="db4c6-116">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="db4c6-117">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="db4c6-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a><span data-ttu-id="db4c6-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="db4c6-118">See also</span></span>

- [<span data-ttu-id="db4c6-119">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="db4c6-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="db4c6-120">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="db4c6-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="db4c6-121">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="db4c6-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="db4c6-122">アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="db4c6-122">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="db4c6-123">アクセシビリティ レベル</span><span class="sxs-lookup"><span data-stu-id="db4c6-123">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="db4c6-124">修飾子</span><span class="sxs-lookup"><span data-stu-id="db4c6-124">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="db4c6-125">public</span><span class="sxs-lookup"><span data-stu-id="db4c6-125">public</span></span>](public.md)
- [<span data-ttu-id="db4c6-126">private</span><span class="sxs-lookup"><span data-stu-id="db4c6-126">private</span></span>](private.md)
- [<span data-ttu-id="db4c6-127">internal</span><span class="sxs-lookup"><span data-stu-id="db4c6-127">internal</span></span>](internal.md)
- <span data-ttu-id="db4c6-128">[Internal Virtual キーワードのセキュリティ関連事項](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="db4c6-128">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
