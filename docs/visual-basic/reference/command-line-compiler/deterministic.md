---
title: -deterministic
ms.date: 04/11/2018
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
ms.openlocfilehash: 95c9add0521208ef04ff47c071a2e04abc968f27
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59480639"
---
# <a name="-deterministic"></a><span data-ttu-id="1a7d3-102">-deterministic</span><span class="sxs-lookup"><span data-stu-id="1a7d3-102">-deterministic</span></span>

<span data-ttu-id="1a7d3-103">同一の入力に対して、バイト単位の出力がコンパイル全体で同一のアセンブリをコンパイラに生成させます。</span><span class="sxs-lookup"><span data-stu-id="1a7d3-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span>

## <a name="syntax"></a><span data-ttu-id="1a7d3-104">構文</span><span class="sxs-lookup"><span data-stu-id="1a7d3-104">Syntax</span></span>

```
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="1a7d3-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="1a7d3-105">Remarks</span></span>

<span data-ttu-id="1a7d3-106">既定では、コンパイラはタイムスタンプと乱数から生成された GUID を追加するため、指定した入力のセットからのコンパイラの出力は固有になります。</span><span class="sxs-lookup"><span data-stu-id="1a7d3-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="1a7d3-107">`-deterministic` オプションを使用して、*決定論的アセンブリ*を生成します。そのバイナリ コンテンツは、入力が同じである限り、コンパイル全体で同一になります。</span><span class="sxs-lookup"><span data-stu-id="1a7d3-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="1a7d3-108">コンパイラでは決定性のために次の入力が考慮されます。</span><span class="sxs-lookup"><span data-stu-id="1a7d3-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="1a7d3-109">コマンド ライン パラメーターのシーケンス。</span><span class="sxs-lookup"><span data-stu-id="1a7d3-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="1a7d3-110">コンパイラの .rsp 応答ファイルの内容。</span><span class="sxs-lookup"><span data-stu-id="1a7d3-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="1a7d3-111">使用されるコンパイラの正確なバージョン、およびその参照先のアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="1a7d3-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="1a7d3-112">現在のディレクトリ パス。</span><span class="sxs-lookup"><span data-stu-id="1a7d3-112">The current directory path.</span></span>
- <span data-ttu-id="1a7d3-113">すべてのファイルのバイナリ コンテンツは、以下を含めて、直接または間接のいずれかでコンパイラに明示的に渡されます。</span><span class="sxs-lookup"><span data-stu-id="1a7d3-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
  - <span data-ttu-id="1a7d3-114">ソース ファイル</span><span class="sxs-lookup"><span data-stu-id="1a7d3-114">Source files</span></span>
  - <span data-ttu-id="1a7d3-115">参照アセンブリ</span><span class="sxs-lookup"><span data-stu-id="1a7d3-115">Referenced assemblies</span></span>
  - <span data-ttu-id="1a7d3-116">参照モジュール</span><span class="sxs-lookup"><span data-stu-id="1a7d3-116">Referenced modules</span></span>
  - <span data-ttu-id="1a7d3-117">リソース</span><span class="sxs-lookup"><span data-stu-id="1a7d3-117">Resources</span></span>
  - <span data-ttu-id="1a7d3-118">厳密な名前のキー ファイル</span><span class="sxs-lookup"><span data-stu-id="1a7d3-118">The strong name key file</span></span>
  - <span data-ttu-id="1a7d3-119">@ 応答ファイル</span><span class="sxs-lookup"><span data-stu-id="1a7d3-119">@ response files</span></span>
  - <span data-ttu-id="1a7d3-120">アナライザー</span><span class="sxs-lookup"><span data-stu-id="1a7d3-120">Analyzers</span></span>
  - <span data-ttu-id="1a7d3-121">ルールセット</span><span class="sxs-lookup"><span data-stu-id="1a7d3-121">Rulesets</span></span>
  - <span data-ttu-id="1a7d3-122">アナライザーによって使用される可能性がある追加のファイル</span><span class="sxs-lookup"><span data-stu-id="1a7d3-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="1a7d3-123">現在のカルチャ (診断と例外メッセージが生成される言語)。</span><span class="sxs-lookup"><span data-stu-id="1a7d3-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="1a7d3-124">エンコードが指定されていない場合の既定のエンコード (または現在のコード ページ)。</span><span class="sxs-lookup"><span data-stu-id="1a7d3-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="1a7d3-125">コンパイラの検索パス上のファイルの有無、および内容 (たとえば、`/lib` や `/recurse` で指定)。</span><span class="sxs-lookup"><span data-stu-id="1a7d3-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `/lib` or `/recurse`).</span></span>
- <span data-ttu-id="1a7d3-126">コンパイラが実行される CLR プラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="1a7d3-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="1a7d3-127">`%LIBPATH%` の値。アナライザーの依存関係の読み込みに影響する場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a7d3-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="1a7d3-128">ソースを公開用に利用できる場合、バイナリが信頼できる発行元からコンパイルされているかどうかを確立するために、決定論的コンパイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1a7d3-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="1a7d3-129">これは、バイナリへの変更に依存しているビルド ステップを実行する必要があるかどうかを決定するために、継続的なビルド システムで役立つ場合もあります。</span><span class="sxs-lookup"><span data-stu-id="1a7d3-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a7d3-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a7d3-130">See also</span></span>

- [<span data-ttu-id="1a7d3-131">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="1a7d3-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="1a7d3-132">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="1a7d3-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
