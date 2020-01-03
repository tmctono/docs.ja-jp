---
title: -refout
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: 3649a24a52cc6a448ea7cf4d850915adf02147fb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348650"
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="9c10b-102">-refout (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c10b-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="9c10b-103">**-refout** オプションは、参照アセンブリを出力するファイル パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9c10b-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="9c10b-104">構文</span><span class="sxs-lookup"><span data-stu-id="9c10b-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="9c10b-105">引数</span><span class="sxs-lookup"><span data-stu-id="9c10b-105">Arguments</span></span>

`filepath`  
<span data-ttu-id="9c10b-106">参照アセンブリのパスとファイル名。</span><span class="sxs-lookup"><span data-stu-id="9c10b-106">The path and filename of the reference assembly.</span></span> <span data-ttu-id="9c10b-107">通常、プライマリアセンブリのサブフォルダーに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c10b-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="9c10b-108">(MSBuild で使用される) 推奨規則は、プライマリ アセンブリに相対する "ref/" サブ フォルダー内に参照アセンブリを配置することです。</span><span class="sxs-lookup"><span data-stu-id="9c10b-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="9c10b-109">`filepath` 内のすべてのフォルダーが存在している必要があります。コンパイラでは、これらは作成されません。</span><span class="sxs-lookup"><span data-stu-id="9c10b-109">All folders in `filepath` must exist; the compiler does not create them.</span></span>

## <a name="remarks"></a><span data-ttu-id="9c10b-110">コメント</span><span class="sxs-lookup"><span data-stu-id="9c10b-110">Remarks</span></span>

<span data-ttu-id="9c10b-111">Visual Basic では、バージョン15.3 以降の `-refout` スイッチがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9c10b-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="9c10b-112">参照アセンブリは、ライブラリのパブリック API サーフェイスを表すために必要最小限のメタデータのみを含む特殊なアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="9c10b-112">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="9c10b-113">これには、ビルド ツールでアセンブリを参照するときに重要なすべてのメンバーの宣言が含まれます。ただし、すべてのメンバーの実装と、その API コントラクトに影響を与えないプライベート メンバーの宣言は除外されます。</span><span class="sxs-lookup"><span data-stu-id="9c10b-113">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="9c10b-114">詳細については、.NET のガイドの「[参照アセンブリ](../../../standard/assembly/reference-assemblies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c10b-114">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="9c10b-115">`-refout` オプションと [`-refonly`](refonly-compiler-option.md) オプションは同時に指定できません。</span><span class="sxs-lookup"><span data-stu-id="9c10b-115">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c10b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c10b-116">See also</span></span>

- [<span data-ttu-id="9c10b-117">/refonly</span><span class="sxs-lookup"><span data-stu-id="9c10b-117">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="9c10b-118">Visual Basic コマンドラインコンパイラ</span><span class="sxs-lookup"><span data-stu-id="9c10b-118">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="9c10b-119">コンパイルコマンドラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="9c10b-119">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
