---
title: 式ツリーのまとめ
description: 式ツリーを使用して、コードをデータとして解釈する動的なプログラムを作成し、そのコードに基づいて新しい機能を構築する方法についてまとめます。
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: eb687ebd-1149-4453-9fc1-12a084495a66
ms.openlocfilehash: 43715c94b70f1cd7f758cde91ae7c8d1b2f70f9f
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036758"
---
# <a name="expression-trees-summary"></a><span data-ttu-id="3b41d-103">式ツリーのまとめ</span><span class="sxs-lookup"><span data-stu-id="3b41d-103">Expression Trees Summary</span></span>

[<span data-ttu-id="3b41d-104">前へ -- 式の変換</span><span class="sxs-lookup"><span data-stu-id="3b41d-104">Previous -- Translating Expressions</span></span>](expression-trees-translating.md)

<span data-ttu-id="3b41d-105">このシリーズでは、*式ツリー*を使用して、コードをデータとして解釈する動的なプログラムを作成し、そのコードに基づいて新しい機能を構築する方法について説明してきました。</span><span class="sxs-lookup"><span data-stu-id="3b41d-105">In this series, you've seen how you can use *expression trees* to create dynamic programs that interpret code as data and build new functionality based on that code.</span></span>

<span data-ttu-id="3b41d-106">式ツリーを調べれば、アルゴリズムの目的を理解することができます。</span><span class="sxs-lookup"><span data-stu-id="3b41d-106">You can examine expression trees to understand the intent of an algorithm.</span></span> <span data-ttu-id="3b41d-107">そのコードを調べるだけではなく、</span><span class="sxs-lookup"><span data-stu-id="3b41d-107">You can not only examine that code.</span></span> <span data-ttu-id="3b41d-108">元のコードの変更バージョンを表す新しい式ツリーを構築することができます。</span><span class="sxs-lookup"><span data-stu-id="3b41d-108">You can build new expression trees that represent modified versions of the original code.</span></span>

<span data-ttu-id="3b41d-109">また式ツリーは、アルゴリズムを参照して、そのアルゴリズムを別の言語や環境に変換するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="3b41d-109">You can also use expression trees to look at an algorithm, and translate that algorithm into another language or environment.</span></span> 

## <a name="limitations"></a><span data-ttu-id="3b41d-110">制限事項</span><span class="sxs-lookup"><span data-stu-id="3b41d-110">Limitations</span></span>

<span data-ttu-id="3b41d-111">C# の新しい言語要素の中には、式ツリーに正しく変換できないものもあります。</span><span class="sxs-lookup"><span data-stu-id="3b41d-111">There are some newer C# language elements that don't translate well into expression trees.</span></span> <span data-ttu-id="3b41d-112">式ツリーに `await` 式や `async` ラムダ式を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="3b41d-112">Expression trees cannot contain `await` expressions, or `async` lambda expressions.</span></span> <span data-ttu-id="3b41d-113">C# 6 リリースで追加された機能の多くは、式ツリーで記述されたとおりには表示されません。</span><span class="sxs-lookup"><span data-stu-id="3b41d-113">Many of the features added in the C# 6 release don't appear exactly as written in expression trees.</span></span> <span data-ttu-id="3b41d-114">新しい機能は、等価の形式 (以前の構文) で式ツリーに公開されます。</span><span class="sxs-lookup"><span data-stu-id="3b41d-114">Instead, newer features will be exposed in expressions trees in the equivalent, earlier syntax.</span></span> <span data-ttu-id="3b41d-115">このことは、それほど大きな制約にはならない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="3b41d-115">This may not be as much of a limitation as you might think.</span></span> <span data-ttu-id="3b41d-116">実際、式ツリーを解釈するコードは多くの場合、新しい言語機能が導入されても、以前と同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="3b41d-116">In fact, it means that your code that interprets expression trees will likely still work the same when new language features are introduced.</span></span>

<span data-ttu-id="3b41d-117">これらの制限事項があっても、式ツリーでは、データ構造として表されたコードの解釈や変更に依存する動的アルゴリズムを作成することが可能です。</span><span class="sxs-lookup"><span data-stu-id="3b41d-117">Even with these limitations, expression trees do enable you to create dynamic algorithms that rely on interpreting and modifying code that is represented as a data structure.</span></span> <span data-ttu-id="3b41d-118">式ツリーは強力なツールであり、Entity Framework などのリッチなライブラリで目的の機能を達成できる .NET エコシステムの 1 機能です。</span><span class="sxs-lookup"><span data-stu-id="3b41d-118">It's a powerful tool, and it's one of the features of the .NET ecosystem that enables rich libraries such as Entity Framework to accomplish what they do.</span></span>
