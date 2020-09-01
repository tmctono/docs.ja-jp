---
description: protected internal - C# リファレンス
title: protected internal - C# リファレンス
ms.date: 11/15/2017
f1_keywords:
- protectedinternal_CSharpKeyword
author: sputier
ms.openlocfilehash: a7537fba93c0d7145f04c6236d15c11b70f8bf98
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139438"
---
# <a name="protected-internal-c-reference"></a><span data-ttu-id="2c3bf-103">protected internal (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="2c3bf-103">protected internal (C# Reference)</span></span>

<span data-ttu-id="2c3bf-104">キーワード組み合わせ `protected internal` はメンバー アクセス修飾子です。</span><span class="sxs-lookup"><span data-stu-id="2c3bf-104">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="2c3bf-105">protected internal メンバーには、現在のアセンブリから、または包含クラスから派生した型からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2c3bf-105">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="2c3bf-106">`protected internal` と他のアクセス修飾子の比較については、「[アクセシビリティ レベル](accessibility-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c3bf-106">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="2c3bf-107">例</span><span class="sxs-lookup"><span data-stu-id="2c3bf-107">Example</span></span>

<span data-ttu-id="2c3bf-108">基底クラスのプロテクト内部メンバーは、包含アセンブリ内の任意の型からアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2c3bf-108">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="2c3bf-109">派生クラス型の変数経由でアクセスする場合にのみ、別のアセンブリにある派生クラスでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2c3bf-109">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="2c3bf-110">たとえば、次のコード セグメントを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="2c3bf-110">For example, consider the following code segment:</span></span>

```csharp
// Assembly1.cs
// Compile with: /target:library
public class BaseClass
{
   protected internal int myValue = 0;
}

class TestAccess
{
    void Access()
    {
        var baseObject = new BaseClass();
        baseObject.myValue = 5;
    }
}
```

```csharp
// Assembly2.cs
// Compile with: /reference:Assembly1.dll
class DerivedClass : BaseClass
{
    static void Main()
    {
        var baseObject = new BaseClass();
        var derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10;

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
}
```

<span data-ttu-id="2c3bf-111">この例には、2 つのファイル (`Assembly1.cs` と `Assembly2.cs`) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c3bf-111">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="2c3bf-112">最初のファイルには public 基底クラスである `BaseClass` ともう 1 つのクラスである `TestAccess` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c3bf-112">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="2c3bf-113">`BaseClass` は protected internal メンバーの `myValue` を持っています。これは `TestAccess` 型にアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="2c3bf-113">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span>
<span data-ttu-id="2c3bf-114">2 番目のファイルでは、`BaseClass` のインスタンス経由で `myValue` にアクセスしようとするとエラーが発生します。一方で、派生クラス `DerivedClass` のインスタンスからこのメンバーにアクセスすると成功します。</span><span class="sxs-lookup"><span data-stu-id="2c3bf-114">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span>

<span data-ttu-id="2c3bf-115">構造体は継承できないため、構造体メンバーは `protected internal` になりません。</span><span class="sxs-lookup"><span data-stu-id="2c3bf-115">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2c3bf-116">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="2c3bf-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="2c3bf-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c3bf-117">See also</span></span>

- [<span data-ttu-id="2c3bf-118">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="2c3bf-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2c3bf-119">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="2c3bf-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2c3bf-120">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="2c3bf-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="2c3bf-121">アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="2c3bf-121">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="2c3bf-122">アクセシビリティ レベル</span><span class="sxs-lookup"><span data-stu-id="2c3bf-122">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="2c3bf-123">修飾子</span><span class="sxs-lookup"><span data-stu-id="2c3bf-123">Modifiers</span></span>](index.md)
- [<span data-ttu-id="2c3bf-124">public</span><span class="sxs-lookup"><span data-stu-id="2c3bf-124">public</span></span>](public.md)
- [<span data-ttu-id="2c3bf-125">private</span><span class="sxs-lookup"><span data-stu-id="2c3bf-125">private</span></span>](private.md)
- [<span data-ttu-id="2c3bf-126">internal</span><span class="sxs-lookup"><span data-stu-id="2c3bf-126">internal</span></span>](internal.md)
- <span data-ttu-id="2c3bf-127">[Internal Virtual キーワードのセキュリティ関連事項](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2c3bf-127">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
