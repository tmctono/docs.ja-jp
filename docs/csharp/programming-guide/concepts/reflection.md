---
title: リフレクション (C#)
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: a56fb24b63e4d80dbb67b079466b67cd11672023
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "74711661"
---
# <a name="reflection-c"></a><span data-ttu-id="893c7-102">リフレクション (C#)</span><span class="sxs-lookup"><span data-stu-id="893c7-102">Reflection (C#)</span></span>

<span data-ttu-id="893c7-103">リフレクションによって、アセンブリ、モジュール、および型を記述する (<xref:System.Type> 型の) オブジェクトが提供されます。</span><span class="sxs-lookup"><span data-stu-id="893c7-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules, and types.</span></span> <span data-ttu-id="893c7-104">リフレクションを使用すると、動的に型のインスタンスを作成したり、作成したインスタンスを既存のオブジェクトにバインドしたり、さらに既存のオブジェクトから型を取得してそのオブジェクトのメソッドを呼び出したり、フィールドやプロパティにアクセスしたりできます。</span><span class="sxs-lookup"><span data-stu-id="893c7-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="893c7-105">コードで属性を使用している場合は、リフレクションを使用してそれらにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="893c7-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="893c7-106">詳細については、「[属性](../../../standard/attributes/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="893c7-106">For more information, see [Attributes](../../../standard/attributes/index.md).</span></span>

<span data-ttu-id="893c7-107">次の例は、<xref:System.Object.GetType> メソッドを使用して変数の型を取得する簡単なリフレクションを示しています。このメソッドは、`Object` 基底クラスからすべての型に継承されるメソッドです。</span><span class="sxs-lookup"><span data-stu-id="893c7-107">Here's a simple example of reflection using the <xref:System.Object.GetType> method - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>

> [!NOTE]
> <span data-ttu-id="893c7-108">*.cs* ファイルの先頭に `using System;` と `using System.Reflection;` を必ず追加してください。</span><span class="sxs-lookup"><span data-stu-id="893c7-108">Make sure you add `using System;` and `using System.Reflection;` at the top of your *.cs* file.</span></span>

```csharp
// Using GetType to obtain type information:
int i = 42;
Type type = i.GetType();
Console.WriteLine(type);
```

<span data-ttu-id="893c7-109">出力は `System.Int32` になります。</span><span class="sxs-lookup"><span data-stu-id="893c7-109">The output is: `System.Int32`.</span></span>

<span data-ttu-id="893c7-110">次の例では、リフレクションを使用して、読み込まれたアセンブリの完全名を取得します。</span><span class="sxs-lookup"><span data-stu-id="893c7-110">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>

```csharp
// Using Reflection to get information of an Assembly:
Assembly info = typeof(int).Assembly;
Console.WriteLine(info);
```

<span data-ttu-id="893c7-111">出力は `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e` になります。</span><span class="sxs-lookup"><span data-stu-id="893c7-111">The output is: `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`.</span></span>

> [!NOTE]
> <span data-ttu-id="893c7-112">C# の `protected` キーワードと `internal` キーワードは、IL では意味を持たないため、リフレクション API でも使用されません。</span><span class="sxs-lookup"><span data-stu-id="893c7-112">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="893c7-113">IL では、"*ファミリ*" および "*アセンブリ*" という用語がこれに相当します。</span><span class="sxs-lookup"><span data-stu-id="893c7-113">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="893c7-114">リフレクションを使用して `internal` メソッドを指定するには、<xref:System.Reflection.MethodBase.IsAssembly%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="893c7-114">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="893c7-115">`protected internal` メソッドを指定するには、<xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A> を使用します。</span><span class="sxs-lookup"><span data-stu-id="893c7-115">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>

## <a name="reflection-overview"></a><span data-ttu-id="893c7-116">リフレクションの概要</span><span class="sxs-lookup"><span data-stu-id="893c7-116">Reflection overview</span></span>

<span data-ttu-id="893c7-117">リフレクションは、次の場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="893c7-117">Reflection is useful in the following situations:</span></span>

- <span data-ttu-id="893c7-118">プログラムのメタデータ内の属性にアクセスする必要がある。</span><span class="sxs-lookup"><span data-stu-id="893c7-118">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="893c7-119">詳細については、「[属性に格納されている情報の取得](../../../standard/attributes/retrieving-information-stored-in-attributes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="893c7-119">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>
- <span data-ttu-id="893c7-120">アセンブリの型をチェックし、インスタンス化する。</span><span class="sxs-lookup"><span data-stu-id="893c7-120">For examining and instantiating types in an assembly.</span></span>
- <span data-ttu-id="893c7-121">実行時に新しい型を作成する。</span><span class="sxs-lookup"><span data-stu-id="893c7-121">For building new types at runtime.</span></span> <span data-ttu-id="893c7-122"><xref:System.Reflection.Emit> でクラスを使います。</span><span class="sxs-lookup"><span data-stu-id="893c7-122">Use classes in <xref:System.Reflection.Emit>.</span></span>
- <span data-ttu-id="893c7-123">遅延バインディングを実行するために、実行時に作成された型でメソッドにアクセスする。</span><span class="sxs-lookup"><span data-stu-id="893c7-123">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="893c7-124">「[型の動的な読み込みおよび使用](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="893c7-124">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>

## <a name="related-sections"></a><span data-ttu-id="893c7-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="893c7-125">Related sections</span></span>

<span data-ttu-id="893c7-126">詳細情報</span><span class="sxs-lookup"><span data-stu-id="893c7-126">For more information:</span></span>

- [<span data-ttu-id="893c7-127">リフレクション</span><span class="sxs-lookup"><span data-stu-id="893c7-127">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
- [<span data-ttu-id="893c7-128">型情報の表示</span><span class="sxs-lookup"><span data-stu-id="893c7-128">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)
- [<span data-ttu-id="893c7-129">リフレクションとジェネリック型</span><span class="sxs-lookup"><span data-stu-id="893c7-129">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)
- <xref:System.Reflection.Emit>
- [<span data-ttu-id="893c7-130">属性に格納されている情報の取得</span><span class="sxs-lookup"><span data-stu-id="893c7-130">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)

## <a name="see-also"></a><span data-ttu-id="893c7-131">参照</span><span class="sxs-lookup"><span data-stu-id="893c7-131">See also</span></span>

- [<span data-ttu-id="893c7-132">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="893c7-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="893c7-133">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="893c7-133">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
