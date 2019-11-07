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
ms.openlocfilehash: c9d879d1760f543d5a4722977d4dee8bca856016
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739194"
---
# <a name="c-programming-guide"></a><span data-ttu-id="0f20f-102">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="0f20f-102">C# programming guide</span></span>

<span data-ttu-id="0f20f-103">このセクションでは、C# 言語の重要な機能に関する詳細と、.NET Framework 経由でアクセスできる C# の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="0f20f-103">This section provides detailed information on key C# language features and features accessible to C# through the .NET Framework.</span></span>  
  
 <span data-ttu-id="0f20f-104">このセクションの大部分は、C# と一般的なプログラミングの概念について、ある程度の知識を持っていることを前提として説明されています。</span><span class="sxs-lookup"><span data-stu-id="0f20f-104">Most of this section assumes that you already know something about C# and general programming concepts.</span></span> <span data-ttu-id="0f20f-105">プログラミングや C# のまったくの初心者の方は、[C# チュートリアルの概要](../tutorials/intro-to-csharp/index.md) に関するページや [.NET In-Browser Tutorial](https://dotnet.microsoft.com/learn/dotnet/in-browser-tutorial/1)(ブラウザーでの .NET のチュートリアル) を参照してください。プログラミングの予備知識は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0f20f-105">If you are a complete beginner with programming or with C#, you might want to visit the [Introduction to C# Tutorials](../tutorials/intro-to-csharp/index.md) or [.NET In-Browser Tutorial](https://dotnet.microsoft.com/learn/dotnet/in-browser-tutorial/1), where no prior programming knowledge is required.</span></span>  
  
 <span data-ttu-id="0f20f-106">特定のキーワード、演算子、およびプリプロセッサ ディレクティブについては、「[C# リファレンス](../language-reference/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f20f-106">For information about specific keywords, operators and preprocessor directives, see [C# Reference](../language-reference/index.md).</span></span> <span data-ttu-id="0f20f-107">C# 言語の仕様については、「[C# 言語仕様](/dotnet/csharp/language-reference/language-specification/introduction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f20f-107">For information about the C# Language Specification, see [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>  
  
## <a name="program-sections"></a><span data-ttu-id="0f20f-108">プログラムのセクション</span><span class="sxs-lookup"><span data-stu-id="0f20f-108">Program sections</span></span>

[<span data-ttu-id="0f20f-109">インサイド C# プログラム</span><span class="sxs-lookup"><span data-stu-id="0f20f-109">Inside a C# Program</span></span>](./inside-a-program/index.md)  
  
[<span data-ttu-id="0f20f-110">Main() とコマンドライン引数</span><span class="sxs-lookup"><span data-stu-id="0f20f-110">Main() and Command-Line Arguments</span></span>](./main-and-command-args/index.md)  

## <a name="language-sections"></a><span data-ttu-id="0f20f-111">言語セクション</span><span class="sxs-lookup"><span data-stu-id="0f20f-111">Language Sections</span></span>

[<span data-ttu-id="0f20f-112">ステートメント、式、および演算子</span><span class="sxs-lookup"><span data-stu-id="0f20f-112">Statements, Expressions, and Operators</span></span>](./statements-expressions-operators/index.md)  

 [<span data-ttu-id="0f20f-113">型</span><span class="sxs-lookup"><span data-stu-id="0f20f-113">Types</span></span>](./types/index.md)  

 [<span data-ttu-id="0f20f-114">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="0f20f-114">Classes and Structs</span></span>](./classes-and-structs/index.md)  
  
 [<span data-ttu-id="0f20f-115">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0f20f-115">Interfaces</span></span>](./interfaces/index.md)  

 [<span data-ttu-id="0f20f-116">列挙型</span><span class="sxs-lookup"><span data-stu-id="0f20f-116">Enumeration Types</span></span>](./enumeration-types.md)  
  
 [<span data-ttu-id="0f20f-117">デリゲート</span><span class="sxs-lookup"><span data-stu-id="0f20f-117">Delegates</span></span>](./delegates/index.md)  

 [<span data-ttu-id="0f20f-118">配列</span><span class="sxs-lookup"><span data-stu-id="0f20f-118">Arrays</span></span>](./arrays/index.md)  
  
 [<span data-ttu-id="0f20f-119">文字列</span><span class="sxs-lookup"><span data-stu-id="0f20f-119">Strings</span></span>](./strings/index.md)  
  
 [<span data-ttu-id="0f20f-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0f20f-120">Properties</span></span>](./classes-and-structs/properties.md)  
  
 [<span data-ttu-id="0f20f-121">インデクサー</span><span class="sxs-lookup"><span data-stu-id="0f20f-121">Indexers</span></span>](./indexers/index.md)  
  
 [<span data-ttu-id="0f20f-122">イベント</span><span class="sxs-lookup"><span data-stu-id="0f20f-122">Events</span></span>](./events/index.md)  
  
 [<span data-ttu-id="0f20f-123">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="0f20f-123">Generics</span></span>](./generics/index.md)  
  
 [<span data-ttu-id="0f20f-124">反復子</span><span class="sxs-lookup"><span data-stu-id="0f20f-124">Iterators</span></span>](./concepts/iterators.md)
  
 [<span data-ttu-id="0f20f-125">LINQ クエリ式</span><span class="sxs-lookup"><span data-stu-id="0f20f-125">LINQ Query Expressions</span></span>](../linq/index.md)  
  
 [<span data-ttu-id="0f20f-126">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="0f20f-126">Lambda Expressions</span></span>](./statements-expressions-operators/lambda-expressions.md)  
  
 [<span data-ttu-id="0f20f-127">名前空間</span><span class="sxs-lookup"><span data-stu-id="0f20f-127">Namespaces</span></span>](./namespaces/index.md)  
  
 [<span data-ttu-id="0f20f-128">アンセーフ コードとポインター</span><span class="sxs-lookup"><span data-stu-id="0f20f-128">Unsafe Code and Pointers</span></span>](./unsafe-code-pointers/index.md)  
  
 [<span data-ttu-id="0f20f-129">XML ドキュメント コメント</span><span class="sxs-lookup"><span data-stu-id="0f20f-129">XML Documentation Comments</span></span>](./xmldoc/index.md)  
  
## <a name="platform-sections"></a><span data-ttu-id="0f20f-130">プラットフォーム セクション</span><span class="sxs-lookup"><span data-stu-id="0f20f-130">Platform Sections</span></span>

 [<span data-ttu-id="0f20f-131">アプリケーション ドメイン</span><span class="sxs-lookup"><span data-stu-id="0f20f-131">Application Domains</span></span>](../../framework/app-domains/application-domains.md)  
  
 [<span data-ttu-id="0f20f-132">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="0f20f-132">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
  
 [<span data-ttu-id="0f20f-133">属性</span><span class="sxs-lookup"><span data-stu-id="0f20f-133">Attributes</span></span>](./concepts/attributes/index.md)  
  
 [<span data-ttu-id="0f20f-134">コレクション</span><span class="sxs-lookup"><span data-stu-id="0f20f-134">Collections</span></span>](./concepts/collections.md)  
  
 [<span data-ttu-id="0f20f-135">例外と例外処理</span><span class="sxs-lookup"><span data-stu-id="0f20f-135">Exceptions and Exception Handling</span></span>](./exceptions/index.md)  
  
 [<span data-ttu-id="0f20f-136">ファイル システムとレジストリ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="0f20f-136">File System and the Registry (C# Programming Guide)</span></span>](./file-system/index.md)  
  
 [<span data-ttu-id="0f20f-137">相互運用性</span><span class="sxs-lookup"><span data-stu-id="0f20f-137">Interoperability</span></span>](./interop/index.md)  
  
 [<span data-ttu-id="0f20f-138">リフレクション</span><span class="sxs-lookup"><span data-stu-id="0f20f-138">Reflection</span></span>](./concepts/reflection.md)  
  
## <a name="see-also"></a><span data-ttu-id="0f20f-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f20f-139">See also</span></span>

- [<span data-ttu-id="0f20f-140">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="0f20f-140">C# Reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="0f20f-141">C#</span><span class="sxs-lookup"><span data-stu-id="0f20f-141">C#</span></span>](../index.md)
