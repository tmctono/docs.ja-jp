---
title: -refonly (C# コンパイラ オプション)
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: 856b65d3b2217dbe5d53ecda00723b47247d80a4
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72773849"
---
# <a name="-refonly-c-compiler-options"></a><span data-ttu-id="38d85-102">-refonly (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="38d85-102">-refonly (C# Compiler Options)</span></span>

<span data-ttu-id="38d85-103">**-refonly** オプションは、実装アセンブリではなく、参照アセンブリをプライマリ出力として出力することを示します。</span><span class="sxs-lookup"><span data-stu-id="38d85-103">The **-refonly** option indicates that a reference assembly should be output instead of an implementation assembly, as the primary output.</span></span> <span data-ttu-id="38d85-104">`-refonly` パラメーターは、参照アセンブリを実行できない場合に、PDB の出力を暗黙的に無効にします。</span><span class="sxs-lookup"><span data-stu-id="38d85-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span> <span data-ttu-id="38d85-105">このオプションは、MSBuild の [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) プロジェクト プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="38d85-105">This option corresponds to the [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="38d85-106">構文</span><span class="sxs-lookup"><span data-stu-id="38d85-106">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="38d85-107">解説</span><span class="sxs-lookup"><span data-stu-id="38d85-107">Remarks</span></span>

<span data-ttu-id="38d85-108">参照アセンブリは、ライブラリのパブリック API サーフェイスを表すために必要最小限のメタデータのみを含む特殊なアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="38d85-108">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="38d85-109">これには、ビルド ツールでアセンブリを参照するときに重要なすべてのメンバーの宣言が含まれます。ただし、すべてのメンバーの実装と、その API コントラクトに影響を与えないプライベート メンバーの宣言は除外されます。</span><span class="sxs-lookup"><span data-stu-id="38d85-109">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="38d85-110">詳細については、.NET のガイドの「[参照アセンブリ](../../../standard/assembly/reference-assemblies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38d85-110">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="38d85-111">`-refonly` オプションと [`-refout`](refout-compiler-option.md) オプションは同時に指定できません。</span><span class="sxs-lookup"><span data-stu-id="38d85-111">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="38d85-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="38d85-112">See also</span></span>

- [<span data-ttu-id="38d85-113">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="38d85-113">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="38d85-114">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="38d85-114">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
