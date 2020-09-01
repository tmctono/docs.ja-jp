---
description: extern エイリアス - C# リファレンス
title: extern エイリアス - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: 301ae06ec02fa6f09257dc87383bc2ec7f589b6d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139009"
---
# <a name="extern-alias-c-reference"></a><span data-ttu-id="4f949-103">extern alias (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="4f949-103">extern alias (C# Reference)</span></span>
<span data-ttu-id="4f949-104">場合によっては、同じ完全修飾型名を持つ、2 つのバージョンのアセンブリを参照する必要が生じることもあります。</span><span class="sxs-lookup"><span data-stu-id="4f949-104">You might have to reference two versions of assemblies that have the same fully-qualified type names.</span></span> <span data-ttu-id="4f949-105">たとえば、同じアプリケーション内で、2 つ以上のバージョンのアセンブリを使用する必要が生じることもあるでしょう。</span><span class="sxs-lookup"><span data-stu-id="4f949-105">For example, you might have to use two or more versions of an assembly in the same application.</span></span> <span data-ttu-id="4f949-106">外部アセンブリ エイリアスを使用すれば、各アセンブリの名前空間を、エイリアスを付けたルート レベルの名前空間内でラップして、それらを同じファイル内で使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4f949-106">By using an external assembly alias, the namespaces from each assembly can be wrapped inside root-level namespaces named by the alias, which enables them to be used in the same file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f949-107">[extern](./extern.md) キーワードは、アンマネージ コードで記述されたメソッドを宣言するために、メソッド修飾子として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f949-107">The [extern](./extern.md) keyword is also used as a method modifier, declaring a method written in unmanaged code.</span></span>  
  
 <span data-ttu-id="4f949-108">同じ完全修飾型名を持つ 2 つのアセンブリを参照するには、コマンド プロンプトで次のようにエイリアスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f949-108">To reference two assemblies with the same fully-qualified type names, an alias must be specified at a command prompt, as follows:</span></span>  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 <span data-ttu-id="4f949-109">これにより、外部エイリアス `GridV1` および `GridV2` が作成されます。</span><span class="sxs-lookup"><span data-stu-id="4f949-109">This creates the external aliases `GridV1` and `GridV2`.</span></span> <span data-ttu-id="4f949-110">これらのエイリアスをプログラム内から使用するには、`extern` キーワードを使用してそれらを参照します。</span><span class="sxs-lookup"><span data-stu-id="4f949-110">To use these aliases from within a program, reference them by using the `extern` keyword.</span></span> <span data-ttu-id="4f949-111">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4f949-111">For example:</span></span>  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 <span data-ttu-id="4f949-112">各 extern エイリアスの宣言では、グローバル名前空間に対応する (ただし、グローバル名前空間内にはない) 追加のルート レベル名前空間が導入されています。</span><span class="sxs-lookup"><span data-stu-id="4f949-112">Each extern alias declaration introduces an additional root-level namespace that parallels (but does not lie within) the global namespace.</span></span> <span data-ttu-id="4f949-113">そのため、各アセンブリの型は、適切な名前空間エイリアスをルートに持つ完全修飾名を使用して、明確に参照することができます。</span><span class="sxs-lookup"><span data-stu-id="4f949-113">Thus types from each assembly can be referred to without ambiguity by using their fully qualified name, rooted in the appropriate namespace-alias.</span></span>  
  
 <span data-ttu-id="4f949-114">前の例では、`GridV1::Grid` が `grid.dll` からのグリッド コントロールで、`GridV2::Grid` が `grid20.dll` からのグリッド コントロールになります。</span><span class="sxs-lookup"><span data-stu-id="4f949-114">In the previous example, `GridV1::Grid` would be the grid control from `grid.dll`, and `GridV2::Grid` would be the grid control from `grid20.dll`.</span></span>  
  
## <a name="using-visual-studio"></a><span data-ttu-id="4f949-115">Visual Studio の使用</span><span class="sxs-lookup"><span data-stu-id="4f949-115">Using Visual Studio</span></span>

<span data-ttu-id="4f949-116">Visual Studio を使用している場合は、同様の方法でエイリアスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4f949-116">If you are using Visual Studio, aliases can be provided in similar way.</span></span>

<span data-ttu-id="4f949-117">Visual Studio のプロジェクトに、*grid.dll* と *grid20.dll* の参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="4f949-117">Add reference of *grid.dll* and *grid20.dll* to your project in Visual Studio.</span></span> <span data-ttu-id="4f949-118">プロパティ タブを開き、エイリアスをグローバルから GridV1 および GridV2 にそれぞれ変更します。</span><span class="sxs-lookup"><span data-stu-id="4f949-118">Open a property tab and change the Aliases from global to GridV1 and GridV2 respectively.</span></span>

<span data-ttu-id="4f949-119">上記と同じ方法でこれらのエイリアスを使用します</span><span class="sxs-lookup"><span data-stu-id="4f949-119">Use these aliases the same way above</span></span>

```csharp
 extern alias GridV1;  
  
 extern alias GridV2;  
```

<span data-ttu-id="4f949-120">これで、"*using エイリアス ディレクティブ*" を使用して、名前空間または型のエイリアスを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4f949-120">Now you can create alias for a namespace or a type by *using alias directive*.</span></span> <span data-ttu-id="4f949-121">詳細については、[using ディレクティブ](using-directive.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4f949-121">For more information, see [using directive](using-directive.md).</span></span>

```csharp
using Class1V1 = GridV1::Namespace.Class1;

using Class1V2 = GridV2::Namespace.Class1;
```

## <a name="c-language-specification"></a><span data-ttu-id="4f949-122">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="4f949-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4f949-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f949-123">See also</span></span>

- [<span data-ttu-id="4f949-124">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="4f949-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4f949-125">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="4f949-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4f949-126">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="4f949-126">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="4f949-127">::演算子</span><span class="sxs-lookup"><span data-stu-id="4f949-127">:: Operator</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="4f949-128">-reference (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="4f949-128">-reference (C# Compiler Options)</span></span>](../compiler-options/reference-compiler-option.md)
