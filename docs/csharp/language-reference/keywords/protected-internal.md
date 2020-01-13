---
title: protected internal - C# リファレンス
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 877df74b51fb859043171619f5687ecddb8409d1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713197"
---
# <a name="protected-internal-c-reference"></a><span data-ttu-id="7a651-102">protected internal (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="7a651-102">protected internal (C# Reference)</span></span>

<span data-ttu-id="7a651-103">キーワード組み合わせ `protected internal` はメンバー アクセス修飾子です。</span><span class="sxs-lookup"><span data-stu-id="7a651-103">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="7a651-104">protected internal メンバーには、現在のアセンブリから、または包含クラスから派生した型からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7a651-104">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="7a651-105">`protected internal` と他のアクセス修飾子の比較については、「[アクセシビリティ レベル](accessibility-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a651-105">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="7a651-106">例</span><span class="sxs-lookup"><span data-stu-id="7a651-106">Example</span></span>

<span data-ttu-id="7a651-107">基底クラスのプロテクト内部メンバーは、包含アセンブリ内の任意の型からアクセスします。</span><span class="sxs-lookup"><span data-stu-id="7a651-107">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="7a651-108">派生クラス型の変数経由でアクセスする場合にのみ、別のアセンブリにある派生クラスでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7a651-108">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="7a651-109">たとえば、次のコード セグメントを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="7a651-109">For example, consider the following code segment:</span></span>

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

<span data-ttu-id="7a651-110">この例には、2 つのファイル (`Assembly1.cs` と `Assembly2.cs`) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7a651-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="7a651-111">最初のファイルには public 基底クラスである `BaseClass` ともう 1 つのクラスである `TestAccess` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7a651-111">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="7a651-112">`BaseClass` は protected internal メンバーの `myValue` を持っています。これは `TestAccess` 型にアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="7a651-112">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span>
<span data-ttu-id="7a651-113">2 番目のファイルでは、`BaseClass` のインスタンス経由で `myValue` にアクセスしようとするとエラーが発生します。一方で、派生クラス `DerivedClass` のインスタンスからこのメンバーにアクセスすると成功します。</span><span class="sxs-lookup"><span data-stu-id="7a651-113">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span>

<span data-ttu-id="7a651-114">構造体は継承できないため、構造体メンバーは `protected internal` になりません。</span><span class="sxs-lookup"><span data-stu-id="7a651-114">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7a651-115">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="7a651-115">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7a651-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a651-116">See also</span></span>

- [<span data-ttu-id="7a651-117">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="7a651-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7a651-118">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="7a651-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7a651-119">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="7a651-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="7a651-120">アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="7a651-120">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="7a651-121">アクセシビリティ レベル</span><span class="sxs-lookup"><span data-stu-id="7a651-121">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="7a651-122">修飾子</span><span class="sxs-lookup"><span data-stu-id="7a651-122">Modifiers</span></span>](index.md)
- [<span data-ttu-id="7a651-123">public</span><span class="sxs-lookup"><span data-stu-id="7a651-123">public</span></span>](public.md)
- [<span data-ttu-id="7a651-124">private</span><span class="sxs-lookup"><span data-stu-id="7a651-124">private</span></span>](private.md)
- [<span data-ttu-id="7a651-125">internal</span><span class="sxs-lookup"><span data-stu-id="7a651-125">internal</span></span>](internal.md)
- <span data-ttu-id="7a651-126">[Internal Virtual キーワードのセキュリティ関連事項](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7a651-126">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
