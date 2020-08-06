---
title: extern エイリアス - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: 891e56b064f8a327abe28293223a85b9d95e8fd3
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301815"
---
# <a name="extern-alias-c-reference"></a><span data-ttu-id="90f30-102">extern alias (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="90f30-102">extern alias (C# Reference)</span></span>
<span data-ttu-id="90f30-103">場合によっては、同じ完全修飾型名を持つ、2 つのバージョンのアセンブリを参照する必要が生じることもあります。</span><span class="sxs-lookup"><span data-stu-id="90f30-103">You might have to reference two versions of assemblies that have the same fully-qualified type names.</span></span> <span data-ttu-id="90f30-104">たとえば、同じアプリケーション内で、2 つ以上のバージョンのアセンブリを使用する必要が生じることもあるでしょう。</span><span class="sxs-lookup"><span data-stu-id="90f30-104">For example, you might have to use two or more versions of an assembly in the same application.</span></span> <span data-ttu-id="90f30-105">外部アセンブリ エイリアスを使用すれば、各アセンブリの名前空間を、エイリアスを付けたルート レベルの名前空間内でラップして、それらを同じファイル内で使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="90f30-105">By using an external assembly alias, the namespaces from each assembly can be wrapped inside root-level namespaces named by the alias, which enables them to be used in the same file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90f30-106">[extern](./extern.md) キーワードは、アンマネージ コードで記述されたメソッドを宣言するために、メソッド修飾子として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="90f30-106">The [extern](./extern.md) keyword is also used as a method modifier, declaring a method written in unmanaged code.</span></span>  
  
 <span data-ttu-id="90f30-107">同じ完全修飾型名を持つ 2 つのアセンブリを参照するには、コマンド プロンプトで次のようにエイリアスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90f30-107">To reference two assemblies with the same fully-qualified type names, an alias must be specified at a command prompt, as follows:</span></span>  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 <span data-ttu-id="90f30-108">これにより、外部エイリアス `GridV1` および `GridV2` が作成されます。</span><span class="sxs-lookup"><span data-stu-id="90f30-108">This creates the external aliases `GridV1` and `GridV2`.</span></span> <span data-ttu-id="90f30-109">これらのエイリアスをプログラム内から使用するには、`extern` キーワードを使用してそれらを参照します。</span><span class="sxs-lookup"><span data-stu-id="90f30-109">To use these aliases from within a program, reference them by using the `extern` keyword.</span></span> <span data-ttu-id="90f30-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="90f30-110">For example:</span></span>  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 <span data-ttu-id="90f30-111">各 extern エイリアスの宣言では、グローバル名前空間に対応する (ただし、グローバル名前空間内にはない) 追加のルート レベル名前空間が導入されています。</span><span class="sxs-lookup"><span data-stu-id="90f30-111">Each extern alias declaration introduces an additional root-level namespace that parallels (but does not lie within) the global namespace.</span></span> <span data-ttu-id="90f30-112">そのため、各アセンブリの型は、適切な名前空間エイリアスをルートに持つ完全修飾名を使用して、明確に参照することができます。</span><span class="sxs-lookup"><span data-stu-id="90f30-112">Thus types from each assembly can be referred to without ambiguity by using their fully qualified name, rooted in the appropriate namespace-alias.</span></span>  
  
 <span data-ttu-id="90f30-113">前の例では、`GridV1::Grid` が `grid.dll` からのグリッド コントロールで、`GridV2::Grid` が `grid20.dll` からのグリッド コントロールになります。</span><span class="sxs-lookup"><span data-stu-id="90f30-113">In the previous example, `GridV1::Grid` would be the grid control from `grid.dll`, and `GridV2::Grid` would be the grid control from `grid20.dll`.</span></span>  
  
## <a name="using-visual-studio"></a><span data-ttu-id="90f30-114">Visual Studio の使用</span><span class="sxs-lookup"><span data-stu-id="90f30-114">Using Visual Studio</span></span>

<span data-ttu-id="90f30-115">Visual Studio を使用している場合は、同様の方法でエイリアスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="90f30-115">If you are using Visual Studio, aliases can be provided in similar way.</span></span>

<span data-ttu-id="90f30-116">Visual Studio のプロジェクトに、*grid.dll* と *grid20.dll* の参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="90f30-116">Add reference of *grid.dll* and *grid20.dll* to your project in Visual Studio.</span></span> <span data-ttu-id="90f30-117">プロパティ タブを開き、エイリアスをグローバルから GridV1 および GridV2 にそれぞれ変更します。</span><span class="sxs-lookup"><span data-stu-id="90f30-117">Open a property tab and change the Aliases from global to GridV1 and GridV2 respectively.</span></span>

<span data-ttu-id="90f30-118">上記と同じ方法でこれらのエイリアスを使用します</span><span class="sxs-lookup"><span data-stu-id="90f30-118">Use these aliases the same way above</span></span>

```csharp
 extern alias GridV1;  
  
 extern alias GridV2;  
```

<span data-ttu-id="90f30-119">これで、"*using エイリアス ディレクティブ*" を使用して、名前空間または型のエイリアスを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="90f30-119">Now you can create alias for a namespace or a type by *using alias directive*.</span></span> <span data-ttu-id="90f30-120">詳細については、[using ディレクティブ](using-directive.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="90f30-120">For more information, see [using directive](using-directive.md).</span></span>

```csharp
using Class1V1 = GridV1::Namespace.Class1;

using Class1V2 = GridV2::Namespace.Class1;
```

## <a name="c-language-specification"></a><span data-ttu-id="90f30-121">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="90f30-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="90f30-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="90f30-122">See also</span></span>

- [<span data-ttu-id="90f30-123">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="90f30-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="90f30-124">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="90f30-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="90f30-125">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="90f30-125">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="90f30-126">::演算子</span><span class="sxs-lookup"><span data-stu-id="90f30-126">:: Operator</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="90f30-127">-reference (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="90f30-127">-reference (C# Compiler Options)</span></span>](../compiler-options/reference-compiler-option.md)
