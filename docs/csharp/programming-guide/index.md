---
title: C# プログラミング ガイド
ms.date: 05/02/2017
f1_keywords:
- cs.langref
helpviewer_keywords:
- reference tables [C#]
- C# language, programming guide
- Visual C#, programming concepts
- C# language, concepts
ms.assetid: ac0f23a2-6bf3-4077-be99-538ae5fd3bc5
ms.openlocfilehash: 5eb9313003f767daf64a5b5c4f229c6c58a018ec
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423244"
---
# <a name="c-programming-guide"></a><span data-ttu-id="709d5-102">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="709d5-102">C# programming guide</span></span>
<span data-ttu-id="709d5-103">このセクションでは、C# 言語の重要な機能に関する詳細と、.NET Framework 経由でアクセスできる C# の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="709d5-103">This section provides detailed information on key C# language features and features accessible to C# through the .NET Framework.</span></span>  
  
 <span data-ttu-id="709d5-104">このセクションの大部分は、C# と一般的なプログラミングの概念について、ある程度の知識を持っていることを前提として説明されています。</span><span class="sxs-lookup"><span data-stu-id="709d5-104">Most of this section assumes that you already know something about C# and general programming concepts.</span></span> <span data-ttu-id="709d5-105">プログラミングや C# のまったくの初心者の方は、[C# チュートリアルの概要](../tutorials/intro-to-csharp/index.md) に関するページや [.NET In-Browser Tutorial](https://dotnet.microsoft.com/learn/dotnet/in-browser-tutorial/1)(ブラウザーでの .NET のチュートリアル) を参照してください。プログラミングの予備知識は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="709d5-105">If you are a complete beginner with programming or with C#, you might want to visit the [Introduction to C# Tutorials](../tutorials/intro-to-csharp/index.md) or [.NET In-Browser Tutorial](https://dotnet.microsoft.com/learn/dotnet/in-browser-tutorial/1), where no prior programming knowledge is required.</span></span>  
  
 <span data-ttu-id="709d5-106">特定のキーワード、演算子、およびプリプロセッサ ディレクティブについては、「[C# リファレンス](../language-reference/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="709d5-106">For information about specific keywords, operators and preprocessor directives, see [C# Reference](../language-reference/index.md).</span></span> <span data-ttu-id="709d5-107">C# 言語の仕様については、「[C# 言語仕様](/dotnet/csharp/language-reference/language-specification/introduction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="709d5-107">For information about the C# Language Specification, see [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>  
  
## <a name="program-sections"></a><span data-ttu-id="709d5-108">プログラムのセクション</span><span class="sxs-lookup"><span data-stu-id="709d5-108">Program sections</span></span>

[<span data-ttu-id="709d5-109">インサイド C# プログラム</span><span class="sxs-lookup"><span data-stu-id="709d5-109">Inside a C# Program</span></span>](./inside-a-program/index.md)  
  
[<span data-ttu-id="709d5-110">Main() とコマンドライン引数</span><span class="sxs-lookup"><span data-stu-id="709d5-110">Main() and Command-Line Arguments</span></span>](./main-and-command-args/index.md)  
 
## <a name="language-sections"></a><span data-ttu-id="709d5-111">言語セクション</span><span class="sxs-lookup"><span data-stu-id="709d5-111">Language Sections</span></span>  
[<span data-ttu-id="709d5-112">ステートメント、式、および演算子</span><span class="sxs-lookup"><span data-stu-id="709d5-112">Statements, Expressions, and Operators</span></span>](./statements-expressions-operators/index.md)  

 [<span data-ttu-id="709d5-113">型</span><span class="sxs-lookup"><span data-stu-id="709d5-113">Types</span></span>](./types/index.md)  

 [<span data-ttu-id="709d5-114">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="709d5-114">Classes and Structs</span></span>](./classes-and-structs/index.md)  
  
 [<span data-ttu-id="709d5-115">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="709d5-115">Interfaces</span></span>](./interfaces/index.md)  

 [<span data-ttu-id="709d5-116">列挙型</span><span class="sxs-lookup"><span data-stu-id="709d5-116">Enumeration Types</span></span>](./enumeration-types.md)  
  
 [<span data-ttu-id="709d5-117">デリゲート</span><span class="sxs-lookup"><span data-stu-id="709d5-117">Delegates</span></span>](./delegates/index.md)  
 
 [<span data-ttu-id="709d5-118">配列</span><span class="sxs-lookup"><span data-stu-id="709d5-118">Arrays</span></span>](./arrays/index.md)  
  
 [<span data-ttu-id="709d5-119">文字列</span><span class="sxs-lookup"><span data-stu-id="709d5-119">Strings</span></span>](./strings/index.md)  
  
 [<span data-ttu-id="709d5-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="709d5-120">Properties</span></span>](./classes-and-structs/properties.md)  
  
 [<span data-ttu-id="709d5-121">インデクサー</span><span class="sxs-lookup"><span data-stu-id="709d5-121">Indexers</span></span>](./indexers/index.md)  
  
 [<span data-ttu-id="709d5-122">イベント</span><span class="sxs-lookup"><span data-stu-id="709d5-122">Events</span></span>](./events/index.md)  
  
 [<span data-ttu-id="709d5-123">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="709d5-123">Generics</span></span>](./generics/index.md)  
  
 [<span data-ttu-id="709d5-124">反復子</span><span class="sxs-lookup"><span data-stu-id="709d5-124">Iterators</span></span>](./concepts/iterators.md)
  
 [<span data-ttu-id="709d5-125">LINQ クエリ式</span><span class="sxs-lookup"><span data-stu-id="709d5-125">LINQ Query Expressions</span></span>](../linq/index.md)  
  
 [<span data-ttu-id="709d5-126">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="709d5-126">Lambda Expressions</span></span>](./statements-expressions-operators/lambda-expressions.md)  
  
 [<span data-ttu-id="709d5-127">名前空間</span><span class="sxs-lookup"><span data-stu-id="709d5-127">Namespaces</span></span>](./namespaces/index.md)  
  
 [<span data-ttu-id="709d5-128">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="709d5-128">Nullable value types</span></span>](./nullable-types/index.md)  
  
 [<span data-ttu-id="709d5-129">アンセーフ コードとポインター</span><span class="sxs-lookup"><span data-stu-id="709d5-129">Unsafe Code and Pointers</span></span>](./unsafe-code-pointers/index.md)  
  
 [<span data-ttu-id="709d5-130">XML ドキュメント コメント</span><span class="sxs-lookup"><span data-stu-id="709d5-130">XML Documentation Comments</span></span>](./xmldoc/index.md)  
  
## <a name="platform-sections"></a><span data-ttu-id="709d5-131">プラットフォーム セクション</span><span class="sxs-lookup"><span data-stu-id="709d5-131">Platform Sections</span></span>  
 [<span data-ttu-id="709d5-132">アプリケーション ドメイン</span><span class="sxs-lookup"><span data-stu-id="709d5-132">Application Domains</span></span>](../../framework/app-domains/application-domains.md)  
  
 [<span data-ttu-id="709d5-133">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="709d5-133">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
  
 [<span data-ttu-id="709d5-134">属性</span><span class="sxs-lookup"><span data-stu-id="709d5-134">Attributes</span></span>](./concepts/attributes/index.md)  
  
 [<span data-ttu-id="709d5-135">コレクション</span><span class="sxs-lookup"><span data-stu-id="709d5-135">Collections</span></span>](./concepts/collections.md)  
  
 [<span data-ttu-id="709d5-136">例外と例外処理</span><span class="sxs-lookup"><span data-stu-id="709d5-136">Exceptions and Exception Handling</span></span>](./exceptions/index.md)  
  
 [<span data-ttu-id="709d5-137">ファイル システムとレジストリ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="709d5-137">File System and the Registry (C# Programming Guide)</span></span>](./file-system/index.md)  
  
 [<span data-ttu-id="709d5-138">相互運用性</span><span class="sxs-lookup"><span data-stu-id="709d5-138">Interoperability</span></span>](./interop/index.md)  
  
 [<span data-ttu-id="709d5-139">リフレクション</span><span class="sxs-lookup"><span data-stu-id="709d5-139">Reflection</span></span>](./concepts/reflection.md)  
  
## <a name="see-also"></a><span data-ttu-id="709d5-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="709d5-140">See also</span></span>

- [<span data-ttu-id="709d5-141">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="709d5-141">C# Reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="709d5-142">C#</span><span class="sxs-lookup"><span data-stu-id="709d5-142">C#</span></span>](../index.md)
