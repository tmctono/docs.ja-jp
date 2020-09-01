---
description: -deterministic (C# コンパイラ オプション)
title: -deterministic (C# コンパイラ オプション)
ms.date: 04/12/2018
f1_keywords:
- /deterministic
helpviewer_keywords:
- -deterministic compiler option [C#]
- deterministic compiler option [C#]
- /deterministic compiler option [C#]
ms.openlocfilehash: 9d0bcc2957e5a666c21cdc2ce61e74fc90fe3530
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125827"
---
# <a name="-deterministic"></a><span data-ttu-id="3c421-103">-deterministic</span><span class="sxs-lookup"><span data-stu-id="3c421-103">-deterministic</span></span>

<span data-ttu-id="3c421-104">同一の入力に対して、バイト単位の出力がコンパイル全体で同一のアセンブリをコンパイラに生成させます。</span><span class="sxs-lookup"><span data-stu-id="3c421-104">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span>

## <a name="syntax"></a><span data-ttu-id="3c421-105">構文</span><span class="sxs-lookup"><span data-stu-id="3c421-105">Syntax</span></span>

```console
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="3c421-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="3c421-106">Remarks</span></span>

<span data-ttu-id="3c421-107">既定では、コンパイラはタイムスタンプと乱数から生成された GUID を追加するため、指定した入力のセットからのコンパイラの出力は固有になります。</span><span class="sxs-lookup"><span data-stu-id="3c421-107">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="3c421-108">`-deterministic` オプションを使用して、*決定論的アセンブリ*を生成します。そのバイナリ コンテンツは、入力が同じである限り、コンパイル全体で同一になります。</span><span class="sxs-lookup"><span data-stu-id="3c421-108">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="3c421-109">コンパイラでは決定性のために次の入力が考慮されます。</span><span class="sxs-lookup"><span data-stu-id="3c421-109">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="3c421-110">コマンド ライン パラメーターのシーケンス。</span><span class="sxs-lookup"><span data-stu-id="3c421-110">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="3c421-111">コンパイラの .rsp 応答ファイルの内容。</span><span class="sxs-lookup"><span data-stu-id="3c421-111">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="3c421-112">使用されるコンパイラの正確なバージョン、およびその参照先のアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="3c421-112">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="3c421-113">現在のディレクトリ パス。</span><span class="sxs-lookup"><span data-stu-id="3c421-113">The current directory path.</span></span>
- <span data-ttu-id="3c421-114">すべてのファイルのバイナリ コンテンツは、以下を含めて、直接または間接のいずれかでコンパイラに明示的に渡されます。</span><span class="sxs-lookup"><span data-stu-id="3c421-114">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
  - <span data-ttu-id="3c421-115">ソース ファイル</span><span class="sxs-lookup"><span data-stu-id="3c421-115">Source files</span></span>
  - <span data-ttu-id="3c421-116">参照アセンブリ</span><span class="sxs-lookup"><span data-stu-id="3c421-116">Referenced assemblies</span></span>
  - <span data-ttu-id="3c421-117">参照モジュール</span><span class="sxs-lookup"><span data-stu-id="3c421-117">Referenced modules</span></span>
  - <span data-ttu-id="3c421-118">リソース</span><span class="sxs-lookup"><span data-stu-id="3c421-118">Resources</span></span>
  - <span data-ttu-id="3c421-119">厳密な名前のキー ファイル</span><span class="sxs-lookup"><span data-stu-id="3c421-119">The strong name key file</span></span>
  - <span data-ttu-id="3c421-120">@ 応答ファイル</span><span class="sxs-lookup"><span data-stu-id="3c421-120">@ response files</span></span>
  - <span data-ttu-id="3c421-121">アナライザー</span><span class="sxs-lookup"><span data-stu-id="3c421-121">Analyzers</span></span>
  - <span data-ttu-id="3c421-122">ルールセット</span><span class="sxs-lookup"><span data-stu-id="3c421-122">Rulesets</span></span>
  - <span data-ttu-id="3c421-123">アナライザーによって使用される可能性がある追加のファイル</span><span class="sxs-lookup"><span data-stu-id="3c421-123">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="3c421-124">現在のカルチャ (診断と例外メッセージが生成される言語)。</span><span class="sxs-lookup"><span data-stu-id="3c421-124">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="3c421-125">エンコードが指定されていない場合の既定のエンコード (または現在のコード ページ)。</span><span class="sxs-lookup"><span data-stu-id="3c421-125">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="3c421-126">コンパイラの検索パス上のファイルの有無、および内容 (たとえば、`-lib` や `-recurse` で指定)。</span><span class="sxs-lookup"><span data-stu-id="3c421-126">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `-lib` or `-recurse`).</span></span>
- <span data-ttu-id="3c421-127">コンパイラが実行される CLR プラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="3c421-127">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="3c421-128">`%LIBPATH%` の値。アナライザーの依存関係の読み込みに影響する場合があります。</span><span class="sxs-lookup"><span data-stu-id="3c421-128">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="3c421-129">ソースを公開用に利用できる場合、バイナリが信頼できる発行元からコンパイルされているかどうかを確立するために、決定論的コンパイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3c421-129">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="3c421-130">これは、バイナリへの変更に依存しているビルド ステップを実行する必要があるかどうかを決定するために、継続的なビルド システムで役立つ場合もあります。</span><span class="sxs-lookup"><span data-stu-id="3c421-130">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c421-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c421-131">See also</span></span>

- [<span data-ttu-id="3c421-132">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="3c421-132">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="3c421-133">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="3c421-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
