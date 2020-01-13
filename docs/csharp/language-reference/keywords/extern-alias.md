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
ms.openlocfilehash: 86202333484933d7449b0c4d8c5a3f1a63cd7775
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713548"
---
# <a name="extern-alias-c-reference"></a><span data-ttu-id="26ecb-102">extern alias (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="26ecb-102">extern alias (C# Reference)</span></span>
<span data-ttu-id="26ecb-103">場合によっては、同じ完全修飾型名を持つ、2 つのバージョンのアセンブリを参照する必要が生じることもあります。</span><span class="sxs-lookup"><span data-stu-id="26ecb-103">You might have to reference two versions of assemblies that have the same fully-qualified type names.</span></span> <span data-ttu-id="26ecb-104">たとえば、同じアプリケーション内で、2 つ以上のバージョンのアセンブリを使用する必要が生じることもあるでしょう。</span><span class="sxs-lookup"><span data-stu-id="26ecb-104">For example, you might have to use two or more versions of an assembly in the same application.</span></span> <span data-ttu-id="26ecb-105">外部アセンブリ エイリアスを使用すれば、各アセンブリの名前空間を、エイリアスを付けたルート レベルの名前空間内でラップして、それらを同じファイル内で使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="26ecb-105">By using an external assembly alias, the namespaces from each assembly can be wrapped inside root-level namespaces named by the alias, which enables them to be used in the same file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26ecb-106">[extern](./extern.md) キーワードは、アンマネージ コードで記述されたメソッドを宣言するために、メソッド修飾子として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="26ecb-106">The [extern](./extern.md) keyword is also used as a method modifier, declaring a method written in unmanaged code.</span></span>  
  
 <span data-ttu-id="26ecb-107">同じ完全修飾型名を持つ 2 つのアセンブリを参照するには、コマンド プロンプトで次のようにエイリアスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26ecb-107">To reference two assemblies with the same fully-qualified type names, an alias must be specified at a command prompt, as follows:</span></span>  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 <span data-ttu-id="26ecb-108">これにより、外部エイリアス `GridV1` および `GridV2` が作成されます。</span><span class="sxs-lookup"><span data-stu-id="26ecb-108">This creates the external aliases `GridV1` and `GridV2`.</span></span> <span data-ttu-id="26ecb-109">これらのエイリアスをプログラム内から使用するには、`extern` キーワードを使用してそれらを参照します。</span><span class="sxs-lookup"><span data-stu-id="26ecb-109">To use these aliases from within a program, reference them by using the `extern` keyword.</span></span> <span data-ttu-id="26ecb-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="26ecb-110">For example:</span></span>  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 <span data-ttu-id="26ecb-111">各 extern エイリアスの宣言では、グローバル名前空間に対応する (ただし、グローバル名前空間内にはない) 追加のルート レベル名前空間が導入されています。</span><span class="sxs-lookup"><span data-stu-id="26ecb-111">Each extern alias declaration introduces an additional root-level namespace that parallels (but does not lie within) the global namespace.</span></span> <span data-ttu-id="26ecb-112">そのため、各アセンブリの型は、適切な名前空間エイリアスをルートに持つ完全修飾名を使用して、明確に参照することができます。</span><span class="sxs-lookup"><span data-stu-id="26ecb-112">Thus types from each assembly can be referred to without ambiguity by using their fully qualified name, rooted in the appropriate namespace-alias.</span></span>  
  
 <span data-ttu-id="26ecb-113">前の例では、`GridV1::Grid` が `grid.dll` からのグリッド コントロールで、`GridV2::Grid` が `grid20.dll` からのグリッド コントロールになります。</span><span class="sxs-lookup"><span data-stu-id="26ecb-113">In the previous example, `GridV1::Grid` would be the grid control from `grid.dll`, and `GridV2::Grid` would be the grid control from `grid20.dll`.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="26ecb-114">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="26ecb-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="26ecb-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="26ecb-115">See also</span></span>

- [<span data-ttu-id="26ecb-116">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="26ecb-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="26ecb-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="26ecb-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="26ecb-118">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="26ecb-118">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="26ecb-119">::演算子</span><span class="sxs-lookup"><span data-stu-id="26ecb-119">:: Operator</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="26ecb-120">-reference (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="26ecb-120">-reference (C# Compiler Options)</span></span>](../compiler-options/reference-compiler-option.md)
