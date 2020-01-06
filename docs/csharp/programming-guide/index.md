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
ms.openlocfilehash: de40369a661c347a2125075e820420af4eb71cac
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337253"
---
# <a name="c-programming-guide"></a><span data-ttu-id="6ba1f-102">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="6ba1f-102">C# programming guide</span></span>

<span data-ttu-id="6ba1f-103">このセクションでは、C# 言語の重要な機能に関する詳細と、.NET Framework 経由でアクセスできる C# の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ba1f-103">This section provides detailed information on key C# language features and features accessible to C# through the .NET Framework.</span></span>  
  
 <span data-ttu-id="6ba1f-104">このセクションの大部分は、C# と一般的なプログラミングの概念について、ある程度の知識を持っていることを前提として説明されています。</span><span class="sxs-lookup"><span data-stu-id="6ba1f-104">Most of this section assumes that you already know something about C# and general programming concepts.</span></span> <span data-ttu-id="6ba1f-105">プログラミングや C# のまったくの初心者の方は、[C# チュートリアルの概要](../tutorials/intro-to-csharp/index.md) に関するページや [.NET In-Browser Tutorial](https://dotnet.microsoft.com/learn/dotnet/in-browser-tutorial/1)(ブラウザーでの .NET のチュートリアル) を参照してください。プログラミングの予備知識は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6ba1f-105">If you are a complete beginner with programming or with C#, you might want to visit the [Introduction to C# Tutorials](../tutorials/intro-to-csharp/index.md) or [.NET In-Browser Tutorial](https://dotnet.microsoft.com/learn/dotnet/in-browser-tutorial/1), where no prior programming knowledge is required.</span></span>  
  
 <span data-ttu-id="6ba1f-106">特定のキーワード、演算子、およびプリプロセッサ ディレクティブについては、「[C# リファレンス](../language-reference/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba1f-106">For information about specific keywords, operators and preprocessor directives, see [C# Reference](../language-reference/index.md).</span></span> <span data-ttu-id="6ba1f-107">C# 言語の仕様については、「[C# 言語仕様](/dotnet/csharp/language-reference/language-specification/introduction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba1f-107">For information about the C# Language Specification, see [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>  
  
## <a name="program-sections"></a><span data-ttu-id="6ba1f-108">プログラムのセクション</span><span class="sxs-lookup"><span data-stu-id="6ba1f-108">Program sections</span></span>

[<span data-ttu-id="6ba1f-109">インサイド C# プログラム</span><span class="sxs-lookup"><span data-stu-id="6ba1f-109">Inside a C# Program</span></span>](./inside-a-program/index.md)  
  
[<span data-ttu-id="6ba1f-110">Main() とコマンドライン引数</span><span class="sxs-lookup"><span data-stu-id="6ba1f-110">Main() and Command-Line Arguments</span></span>](./main-and-command-args/index.md)  

## <a name="language-sections"></a><span data-ttu-id="6ba1f-111">言語セクション</span><span class="sxs-lookup"><span data-stu-id="6ba1f-111">Language Sections</span></span>

[<span data-ttu-id="6ba1f-112">ステートメント、式、および演算子</span><span class="sxs-lookup"><span data-stu-id="6ba1f-112">Statements, Expressions, and Operators</span></span>](./statements-expressions-operators/index.md)  

 [<span data-ttu-id="6ba1f-113">型</span><span class="sxs-lookup"><span data-stu-id="6ba1f-113">Types</span></span>](./types/index.md)  

 [<span data-ttu-id="6ba1f-114">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="6ba1f-114">Classes and Structs</span></span>](./classes-and-structs/index.md)  
  
 [<span data-ttu-id="6ba1f-115">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6ba1f-115">Interfaces</span></span>](./interfaces/index.md)  

 [<span data-ttu-id="6ba1f-116">デリゲート</span><span class="sxs-lookup"><span data-stu-id="6ba1f-116">Delegates</span></span>](./delegates/index.md)  

 [<span data-ttu-id="6ba1f-117">配列</span><span class="sxs-lookup"><span data-stu-id="6ba1f-117">Arrays</span></span>](./arrays/index.md)  
  
 [<span data-ttu-id="6ba1f-118">文字列</span><span class="sxs-lookup"><span data-stu-id="6ba1f-118">Strings</span></span>](./strings/index.md)  
  
 [<span data-ttu-id="6ba1f-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6ba1f-119">Properties</span></span>](./classes-and-structs/properties.md)  
  
 [<span data-ttu-id="6ba1f-120">インデクサー</span><span class="sxs-lookup"><span data-stu-id="6ba1f-120">Indexers</span></span>](./indexers/index.md)  
  
 [<span data-ttu-id="6ba1f-121">イベント</span><span class="sxs-lookup"><span data-stu-id="6ba1f-121">Events</span></span>](./events/index.md)  
  
 [<span data-ttu-id="6ba1f-122">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="6ba1f-122">Generics</span></span>](./generics/index.md)  
  
 [<span data-ttu-id="6ba1f-123">反復子</span><span class="sxs-lookup"><span data-stu-id="6ba1f-123">Iterators</span></span>](./concepts/iterators.md)
  
 [<span data-ttu-id="6ba1f-124">LINQ クエリ式</span><span class="sxs-lookup"><span data-stu-id="6ba1f-124">LINQ Query Expressions</span></span>](../linq/index.md)  
  
 [<span data-ttu-id="6ba1f-125">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="6ba1f-125">Lambda Expressions</span></span>](./statements-expressions-operators/lambda-expressions.md)  
  
 [<span data-ttu-id="6ba1f-126">名前空間</span><span class="sxs-lookup"><span data-stu-id="6ba1f-126">Namespaces</span></span>](./namespaces/index.md)  
  
 [<span data-ttu-id="6ba1f-127">アンセーフ コードとポインター</span><span class="sxs-lookup"><span data-stu-id="6ba1f-127">Unsafe Code and Pointers</span></span>](./unsafe-code-pointers/index.md)  
  
 [<span data-ttu-id="6ba1f-128">XML ドキュメント コメント</span><span class="sxs-lookup"><span data-stu-id="6ba1f-128">XML Documentation Comments</span></span>](./xmldoc/index.md)  
  
## <a name="platform-sections"></a><span data-ttu-id="6ba1f-129">プラットフォーム セクション</span><span class="sxs-lookup"><span data-stu-id="6ba1f-129">Platform Sections</span></span>

 [<span data-ttu-id="6ba1f-130">アプリケーション ドメイン</span><span class="sxs-lookup"><span data-stu-id="6ba1f-130">Application Domains</span></span>](../../framework/app-domains/application-domains.md)  
  
 [<span data-ttu-id="6ba1f-131">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="6ba1f-131">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
  
 [<span data-ttu-id="6ba1f-132">属性</span><span class="sxs-lookup"><span data-stu-id="6ba1f-132">Attributes</span></span>](./concepts/attributes/index.md)  
  
 [<span data-ttu-id="6ba1f-133">コレクション</span><span class="sxs-lookup"><span data-stu-id="6ba1f-133">Collections</span></span>](./concepts/collections.md)  
  
 [<span data-ttu-id="6ba1f-134">例外と例外処理</span><span class="sxs-lookup"><span data-stu-id="6ba1f-134">Exceptions and Exception Handling</span></span>](./exceptions/index.md)  
  
 [<span data-ttu-id="6ba1f-135">ファイル システムとレジストリ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="6ba1f-135">File System and the Registry (C# Programming Guide)</span></span>](./file-system/index.md)  
  
 [<span data-ttu-id="6ba1f-136">相互運用性</span><span class="sxs-lookup"><span data-stu-id="6ba1f-136">Interoperability</span></span>](./interop/index.md)  
  
 [<span data-ttu-id="6ba1f-137">リフレクション</span><span class="sxs-lookup"><span data-stu-id="6ba1f-137">Reflection</span></span>](./concepts/reflection.md)  
  
## <a name="see-also"></a><span data-ttu-id="6ba1f-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ba1f-138">See also</span></span>

- [<span data-ttu-id="6ba1f-139">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="6ba1f-139">C# Reference</span></span>](../language-reference/index.md)
