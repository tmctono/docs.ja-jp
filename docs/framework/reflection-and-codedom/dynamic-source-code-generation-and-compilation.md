---
title: 動的なソース コードの生成とコンパイル
description: Code Document Object Model (CodeDOM) を使用し、.NET で動的ソース コードをコンパイルし、生成します。 CodeDOM 要素は、CodeDOM グラフを形成するためにリンクされています。
ms.date: 03/30/2017
helpviewer_keywords:
- Code Document Object Model
- System.CodeDom namespace
- language-independent source code modeling
- CodeDOM
- multiple languages supported by CodeDOM
- source code in multiple languages
- languages, multiple language support by CodeDOM
ms.assetid: d077a3e8-bd81-4bdf-b6a3-323857ea30fb
ms.openlocfilehash: 7871c27400cf5a7604e509274d5ef3f866070576
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555213"
---
# <a name="compile-and-generate-dynamic-source-code"></a><span data-ttu-id="5a536-104">動的なソース コードをコンパイルして生成する</span><span class="sxs-lookup"><span data-stu-id="5a536-104">Compile and generate dynamic source code</span></span>

<span data-ttu-id="5a536-105">.NET Framework には、CodeDOM (Code Document Object Model) と呼ばれるメカニズムが備わっています。CodeDOM を使用すると、ソース コードを出力するプログラム開発者は、レンダリング対象となるコードを表す単一のモデルに基づいて、実行時に複数のプログラミング言語でソース コードを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="5a536-105">The .NET Framework includes a mechanism called the Code Document Object Model (CodeDOM) that enables developers of programs that emit source code to generate source code in multiple programming languages at run time, based on a single model that represents the code to render.</span></span>  
  
<span data-ttu-id="5a536-106">ソース コードを表現する CodeDOM 要素は相互にリンクされ、CodeDOM グラフと呼ばれるデータ構造体を形成します。これは、ソース コードの構造をモデル化します。</span><span class="sxs-lookup"><span data-stu-id="5a536-106">To represent source code, CodeDOM elements are linked to each other to form a data structure known as a CodeDOM graph, which models the structure of some source code.</span></span>  
  
<span data-ttu-id="5a536-107"><xref:System.CodeDom?displayProperty=fullName> 名前空間は、特定のプログラミング言語に依存せずに、ソース コードの論理構造を表すことができる型を定義します。</span><span class="sxs-lookup"><span data-stu-id="5a536-107">The <xref:System.CodeDom?displayProperty=fullName> namespace defines types that can represent the logical structure of source code, independent of a specific programming language.</span></span> <span data-ttu-id="5a536-108"><xref:System.CodeDom.Compiler?displayProperty=fullName> 名前空間は、CodeDOM グラフからソース コードを生成し、サポートされている言語でソース コードのコンパイルを管理する型を定義します。</span><span class="sxs-lookup"><span data-stu-id="5a536-108">The <xref:System.CodeDom.Compiler?displayProperty=fullName> namespace defines types for generating source code from CodeDOM graphs and managing the compilation of source code in supported languages.</span></span> <span data-ttu-id="5a536-109">サポート対象の言語のセットは、コンパイラの販売元および開発者が拡張できます。</span><span class="sxs-lookup"><span data-stu-id="5a536-109">Compiler vendors or developers can extend the set of supported languages.</span></span>  
  
<span data-ttu-id="5a536-110">言語に依存しないソース コードのモデル化は、プログラムで複数の言語のプログラム モデルのソース コードを生成する必要がある場合や、対象言語が不明な場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5a536-110">Language-independent source code modeling can be valuable when a program needs to generate source code for a program model in multiple languages or for an uncertain target language.</span></span> <span data-ttu-id="5a536-111">たとえば、その言語が CodeDOM でサポートされている場合は、デザイン時に CodeDOM を言語抽象化インターフェイスとして使用し、適切なプログラミング言語でソース コードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="5a536-111">For example, some designers use the CodeDOM as a language abstraction interface to produce source code in the correct programming language, if CodeDOM support for the language is available.</span></span>  
  
<span data-ttu-id="5a536-112">.NET Framework には、<xref:Microsoft.CSharp.CSharpCodeProvider> 用、<xref:Microsoft.JScript.JScriptCodeProvider> 用、および <xref:Microsoft.VisualBasic.VBCodeProvider> 用のコード ジェネレーターとコード コンパイラが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5a536-112">The .NET Framework includes code generators and code compilers for <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider>, and <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a536-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5a536-113">In this section</span></span>

- [<span data-ttu-id="5a536-114">CodeDOM の使用方法</span><span class="sxs-lookup"><span data-stu-id="5a536-114">Using the CodeDOM</span></span>](using-the-codedom.md)

  <span data-ttu-id="5a536-115">CodeDOM の一般的な使用方法を説明し、CodeDOM を使って簡単なオブジェクト グラフを構築する例を示します。</span><span class="sxs-lookup"><span data-stu-id="5a536-115">Describes common uses, and demonstrates building a simple object graph using the CodeDOM.</span></span>  
  
- [<span data-ttu-id="5a536-116">CodeDOM グラフからソース コードを生成してプログラムをコンパイルする</span><span class="sxs-lookup"><span data-stu-id="5a536-116">Generate Source Code and Compile a Program from a CodeDOM Graph</span></span>](generating-and-compiling-source-code-from-a-codedom-graph.md)  

  <span data-ttu-id="5a536-117">ソース コードを生成する方法と、生成されたコードを `System.CodeDom.Compiler` 名前空間で定義されているクラスを使って外部コンパイラでコンパイルする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a536-117">Describes how to generate source code and compile the generated code with an external compiler using classes defined in the `System.CodeDom.Compiler` namespace.</span></span>  
  
- [<span data-ttu-id="5a536-118">方法: CodeDOM を使用して XML ドキュメント ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="5a536-118">How to: Create an XML Documentation File Using CodeDOM</span></span>](how-to-create-an-xml-documentation-file-using-codedom.md)  

  <span data-ttu-id="5a536-119">CodeDOM を使用して XML ドキュメントのコメント付きのコードを生成する方法、および生成されたコードをコンパイルして XML ドキュメントとして出力する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a536-119">Describes how to use CodeDOM to generate code with XML documentation comments, and compile the generated code so that it creates the XML documentation output.</span></span>  
  
- [<span data-ttu-id="5a536-120">方法: CodeDOM を使用してクラスを作成する</span><span class="sxs-lookup"><span data-stu-id="5a536-120">How to: Create a Class Using CodeDOM</span></span>](how-to-create-a-class-using-codedom.md)  

  <span data-ttu-id="5a536-121">CodeDOM を使用してフィールド、プロパティ、メソッド、コンストラクター、およびエントリ ポイントを持つクラスを生成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="5a536-121">Describes how to use CodeDOM to generate a class containing fields, properties, a method, a constructor, and an entry point.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5a536-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a536-122">Reference</span></span>  

- <xref:System.CodeDom>  

  <span data-ttu-id="5a536-123">共通言語ランタイムを対象とするプログラミング言語のコード要素を表す要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="5a536-123">Defines elements that represent code elements in programming languages that target the common language runtime.</span></span>  
  
- <xref:System.CodeDom.Compiler>  

  <span data-ttu-id="5a536-124">実行時にコードを生成およびコンパイルするためのインターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="5a536-124">Defines interfaces for generating and compiling code at run time.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5a536-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a536-125">Related sections</span></span>  

- <span data-ttu-id="5a536-126">「[CodeDOM クイック リファレンス](/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100))」では、ソース コードの要素を表す CodeDOM 要素を簡単に検索するための方法が提供されています。</span><span class="sxs-lookup"><span data-stu-id="5a536-126">[CodeDOM Quick Reference](/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)) provides a quick way for developers to find the CodeDOM elements that represent source code elements.</span></span>
