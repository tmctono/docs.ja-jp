---
title: -refonly
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: b906178abf8d159083d95e41448596d512e857de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348573"
---
# <a name="-refonly-visual-basic"></a><span data-ttu-id="b68ea-102">-refonly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b68ea-102">-refonly (Visual Basic)</span></span>

<span data-ttu-id="b68ea-103">**-Refonly**オプションは、コンパイルのプライマリ出力を実装アセンブリではなく参照アセンブリにする必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="b68ea-103">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="b68ea-104">`-refonly` パラメーターは、参照アセンブリを実行できない場合に、PDB の出力を暗黙的に無効にします。</span><span class="sxs-lookup"><span data-stu-id="b68ea-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="b68ea-105">構文</span><span class="sxs-lookup"><span data-stu-id="b68ea-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="b68ea-106">コメント</span><span class="sxs-lookup"><span data-stu-id="b68ea-106">Remarks</span></span>

<span data-ttu-id="b68ea-107">Visual Basic では、バージョン15.3 以降の `-refonly` スイッチがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b68ea-107">Visual Basic supports the `-refonly` switch starting with version 15.3.</span></span>

<span data-ttu-id="b68ea-108">参照アセンブリは、ライブラリのパブリック API サーフェイスを表すために必要最小限のメタデータのみを含む特殊なアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="b68ea-108">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="b68ea-109">これには、ビルド ツールでアセンブリを参照するときに重要なすべてのメンバーの宣言が含まれます。ただし、すべてのメンバーの実装と、その API コントラクトに影響を与えないプライベート メンバーの宣言は除外されます。</span><span class="sxs-lookup"><span data-stu-id="b68ea-109">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="b68ea-110">詳細については、.NET のガイドの「[参照アセンブリ](../../../standard/assembly/reference-assemblies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b68ea-110">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="b68ea-111">`-refonly` オプションと [`-refout`](refout-compiler-option.md) オプションは同時に指定できません。</span><span class="sxs-lookup"><span data-stu-id="b68ea-111">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="b68ea-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b68ea-112">See also</span></span>

- [<span data-ttu-id="b68ea-113">/refout</span><span class="sxs-lookup"><span data-stu-id="b68ea-113">-refout</span></span>](refout-compiler-option.md)
- [<span data-ttu-id="b68ea-114">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="b68ea-114">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="b68ea-115">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="b68ea-115">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
