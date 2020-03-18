---
title: /refout (C# コンパイラ オプション)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: f48316a1e6f657e3bd0190d269dfe0e875a833d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "72771762"
---
# <a name="-refout-c-compiler-options"></a><span data-ttu-id="878d9-102">/refout (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="878d9-102">-refout (C# Compiler Options)</span></span>

<span data-ttu-id="878d9-103">**-refout** オプションは、参照アセンブリを出力するファイル パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="878d9-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="878d9-104">Emit API では、これを `metadataPeStream` に変換します。</span><span class="sxs-lookup"><span data-stu-id="878d9-104">This translates to `metadataPeStream` in the Emit API.</span></span> <span data-ttu-id="878d9-105">このオプションは、MSBuild の [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) プロジェクト プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="878d9-105">This option corresponds to the [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="878d9-106">構文</span><span class="sxs-lookup"><span data-stu-id="878d9-106">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="878d9-107">引数</span><span class="sxs-lookup"><span data-stu-id="878d9-107">Arguments</span></span>

 <span data-ttu-id="878d9-108">`filepath` 参照アセンブリのファイル パス。</span><span class="sxs-lookup"><span data-stu-id="878d9-108">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="878d9-109">通常はプライマリ アセンブリのファイルパスと一致します。</span><span class="sxs-lookup"><span data-stu-id="878d9-109">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="878d9-110">(MSBuild で使用される) 推奨規則は、プライマリ アセンブリに相対する "ref/" サブ フォルダー内に参照アセンブリを配置することです。</span><span class="sxs-lookup"><span data-stu-id="878d9-110">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="878d9-111">解説</span><span class="sxs-lookup"><span data-stu-id="878d9-111">Remarks</span></span>

<span data-ttu-id="878d9-112">参照アセンブリは、ライブラリのパブリック API サーフェイスを表すために必要最小限のメタデータのみを含む特殊なアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="878d9-112">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="878d9-113">これには、ビルド ツールでアセンブリを参照するときに重要なすべてのメンバーの宣言が含まれます。ただし、すべてのメンバーの実装と、その API コントラクトに影響を与えないプライベート メンバーの宣言は除外されます。</span><span class="sxs-lookup"><span data-stu-id="878d9-113">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="878d9-114">詳細については、.NET のガイドの「[参照アセンブリ](../../../standard/assembly/reference-assemblies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="878d9-114">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="878d9-115">`-refout` オプションと [`-refonly`](refonly-compiler-option.md) オプションは同時に指定できません。</span><span class="sxs-lookup"><span data-stu-id="878d9-115">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="878d9-116">参照</span><span class="sxs-lookup"><span data-stu-id="878d9-116">See also</span></span>

- [<span data-ttu-id="878d9-117">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="878d9-117">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="878d9-118">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="878d9-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
