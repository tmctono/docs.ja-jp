---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 8e64989ac1410b51991027ffcb33e8dae0c0284b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775564"
---
# <a name="-refonly-visual-basic"></a><span data-ttu-id="6aa65-102">-refonly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6aa65-102">-refonly (Visual Basic)</span></span>

<span data-ttu-id="6aa65-103">**-Refonly**オプションは、コンパイルのプライマリ出力を実装アセンブリではなく参照アセンブリにする必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="6aa65-103">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="6aa65-104">`-refonly` パラメーターは、参照アセンブリを実行できない場合に、PDB の出力を暗黙的に無効にします。</span><span class="sxs-lookup"><span data-stu-id="6aa65-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="6aa65-105">構文</span><span class="sxs-lookup"><span data-stu-id="6aa65-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="6aa65-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="6aa65-106">Remarks</span></span>

<span data-ttu-id="6aa65-107">Visual Basic では、バージョン15.3 以降の `-refonly` スイッチがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6aa65-107">Visual Basic supports the `-refonly` switch starting with version 15.3.</span></span>

<span data-ttu-id="6aa65-108">参照アセンブリは、ライブラリのパブリック API サーフェイスを表すために必要な最小限のメタデータのみを含む、特殊な種類のアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="6aa65-108">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="6aa65-109">これには、ビルドツールでアセンブリを参照するときに重要なすべてのメンバーの宣言が含まれますが、API コントラクトに影響を与えないプライベートメンバーのすべてのメンバー実装と宣言は除外されます。</span><span class="sxs-lookup"><span data-stu-id="6aa65-109">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="6aa65-110">詳細については、「.NET での[参照アセンブリ](../../../standard/assembly/reference-assemblies.md)」ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6aa65-110">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="6aa65-111">`-refonly` オプションと [`-refout`](refout-compiler-option.md) オプションは同時に指定できません。</span><span class="sxs-lookup"><span data-stu-id="6aa65-111">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="6aa65-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="6aa65-112">See also</span></span>

- [<span data-ttu-id="6aa65-113">/refout</span><span class="sxs-lookup"><span data-stu-id="6aa65-113">-refout</span></span>](refout-compiler-option.md)
- [<span data-ttu-id="6aa65-114">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="6aa65-114">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="6aa65-115">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="6aa65-115">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
