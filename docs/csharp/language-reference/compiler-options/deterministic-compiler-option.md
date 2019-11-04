---
title: -deterministic (C# コンパイラ オプション)
ms.date: 04/12/2018
f1_keywords:
- /deterministic
helpviewer_keywords:
- -deterministic compiler option [C#]
- deterministic compiler option [C#]
- /deterministic compiler option [C#]
ms.openlocfilehash: ed5d1db4618649391f88affad67e62dd9fc95925
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455188"
---
# <a name="-deterministic"></a><span data-ttu-id="40014-102">-deterministic</span><span class="sxs-lookup"><span data-stu-id="40014-102">-deterministic</span></span>

<span data-ttu-id="40014-103">同一の入力に対して、バイト単位の出力がコンパイル全体で同一のアセンブリをコンパイラに生成させます。</span><span class="sxs-lookup"><span data-stu-id="40014-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span>

## <a name="syntax"></a><span data-ttu-id="40014-104">構文</span><span class="sxs-lookup"><span data-stu-id="40014-104">Syntax</span></span>

```console
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="40014-105">解説</span><span class="sxs-lookup"><span data-stu-id="40014-105">Remarks</span></span>

<span data-ttu-id="40014-106">既定では、コンパイラはタイムスタンプと乱数から生成された GUID を追加するため、指定した入力のセットからのコンパイラの出力は固有になります。</span><span class="sxs-lookup"><span data-stu-id="40014-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="40014-107">`-deterministic` オプションを使用して、*決定論的アセンブリ*を生成します。そのバイナリ コンテンツは、入力が同じである限り、コンパイル全体で同一になります。</span><span class="sxs-lookup"><span data-stu-id="40014-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="40014-108">コンパイラでは決定性のために次の入力が考慮されます。</span><span class="sxs-lookup"><span data-stu-id="40014-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="40014-109">コマンド ライン パラメーターのシーケンス。</span><span class="sxs-lookup"><span data-stu-id="40014-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="40014-110">コンパイラの .rsp 応答ファイルの内容。</span><span class="sxs-lookup"><span data-stu-id="40014-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="40014-111">使用されるコンパイラの正確なバージョン、およびその参照先のアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="40014-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="40014-112">現在のディレクトリ パス。</span><span class="sxs-lookup"><span data-stu-id="40014-112">The current directory path.</span></span>
- <span data-ttu-id="40014-113">すべてのファイルのバイナリ コンテンツは、以下を含めて、直接または間接のいずれかでコンパイラに明示的に渡されます。</span><span class="sxs-lookup"><span data-stu-id="40014-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
  - <span data-ttu-id="40014-114">ソース ファイル</span><span class="sxs-lookup"><span data-stu-id="40014-114">Source files</span></span>
  - <span data-ttu-id="40014-115">参照アセンブリ</span><span class="sxs-lookup"><span data-stu-id="40014-115">Referenced assemblies</span></span>
  - <span data-ttu-id="40014-116">参照モジュール</span><span class="sxs-lookup"><span data-stu-id="40014-116">Referenced modules</span></span>
  - <span data-ttu-id="40014-117">リソース</span><span class="sxs-lookup"><span data-stu-id="40014-117">Resources</span></span>
  - <span data-ttu-id="40014-118">厳密な名前のキー ファイル</span><span class="sxs-lookup"><span data-stu-id="40014-118">The strong name key file</span></span>
  - <span data-ttu-id="40014-119">@ 応答ファイル</span><span class="sxs-lookup"><span data-stu-id="40014-119">@ response files</span></span>
  - <span data-ttu-id="40014-120">アナライザー</span><span class="sxs-lookup"><span data-stu-id="40014-120">Analyzers</span></span>
  - <span data-ttu-id="40014-121">ルールセット</span><span class="sxs-lookup"><span data-stu-id="40014-121">Rulesets</span></span>
  - <span data-ttu-id="40014-122">アナライザーによって使用される可能性がある追加のファイル</span><span class="sxs-lookup"><span data-stu-id="40014-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="40014-123">現在のカルチャ (診断と例外メッセージが生成される言語)。</span><span class="sxs-lookup"><span data-stu-id="40014-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="40014-124">エンコードが指定されていない場合の既定のエンコード (または現在のコード ページ)。</span><span class="sxs-lookup"><span data-stu-id="40014-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="40014-125">コンパイラの検索パス上のファイルの有無、および内容 (たとえば、`-lib` や `-recurse` で指定)。</span><span class="sxs-lookup"><span data-stu-id="40014-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `-lib` or `-recurse`).</span></span>
- <span data-ttu-id="40014-126">コンパイラが実行される CLR プラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="40014-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="40014-127">`%LIBPATH%` の値。アナライザーの依存関係の読み込みに影響する場合があります。</span><span class="sxs-lookup"><span data-stu-id="40014-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="40014-128">ソースを公開用に利用できる場合、バイナリが信頼できる発行元からコンパイルされているかどうかを確立するために、決定論的コンパイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="40014-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="40014-129">これは、バイナリへの変更に依存しているビルド ステップを実行する必要があるかどうかを決定するために、継続的なビルド システムで役立つ場合もあります。</span><span class="sxs-lookup"><span data-stu-id="40014-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span>

## <a name="see-also"></a><span data-ttu-id="40014-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="40014-130">See also</span></span>

- [<span data-ttu-id="40014-131">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="40014-131">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="40014-132">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="40014-132">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
