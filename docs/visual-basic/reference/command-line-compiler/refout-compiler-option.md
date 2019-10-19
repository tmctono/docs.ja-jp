---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: c11d83ff37da41faa3dc6b66a87e2c52c5f6c7ac
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582873"
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="a68c8-102">-refout (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a68c8-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="a68c8-103">**-refout** オプションは、参照アセンブリを出力するファイル パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a68c8-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="a68c8-104">構文</span><span class="sxs-lookup"><span data-stu-id="a68c8-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="a68c8-105">引数</span><span class="sxs-lookup"><span data-stu-id="a68c8-105">Arguments</span></span>

`filepath`  
<span data-ttu-id="a68c8-106">参照アセンブリのパスとファイル名。</span><span class="sxs-lookup"><span data-stu-id="a68c8-106">The path and filename of the reference assembly.</span></span> <span data-ttu-id="a68c8-107">通常、プライマリアセンブリのサブフォルダーに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a68c8-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="a68c8-108">(MSBuild で使用される) 推奨規則は、プライマリ アセンブリに相対する "ref/" サブ フォルダー内に参照アセンブリを配置することです。</span><span class="sxs-lookup"><span data-stu-id="a68c8-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="a68c8-109">@No__t_0 内のすべてのフォルダーが存在している必要があります。コンパイラでは、これらは作成されません。</span><span class="sxs-lookup"><span data-stu-id="a68c8-109">All folders in `filepath` must exist; the compiler does not create them.</span></span>

## <a name="remarks"></a><span data-ttu-id="a68c8-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="a68c8-110">Remarks</span></span>

<span data-ttu-id="a68c8-111">Visual Basic では、バージョン15.3 以降の `-refout` スイッチがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a68c8-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="a68c8-112">参照アセンブリはメタデータのみを格納するアセンブリであり、実装コードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="a68c8-112">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="a68c8-113">これには、匿名型以外のすべての型とメンバーの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a68c8-113">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="a68c8-114">これらのメソッド本体は、1つの `throw null` ステートメントに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="a68c8-114">Their method bodies are replaced with a single `throw null` statement.</span></span> <span data-ttu-id="a68c8-115">(本文なしではなく) `throw null` メソッド本体を使用する理由は、PEVerify が実行されて合格 (したがって、メタデータの完全性を検証する) ことができるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="a68c8-115">The reason for using `throw null` method bodies (as opposed to no bodies) is so that PEVerify can run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="a68c8-116">参照アセンブリには、アセンブリレベルの[referenceassembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute)属性が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a68c8-116">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="a68c8-117">この属性は、ソースで指定できます (指定すると、コンパイラではこれを合成する必要がなくなります)。</span><span class="sxs-lookup"><span data-stu-id="a68c8-117">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="a68c8-118">この属性により、ランタイムは参照アセンブリの読み込みを拒否します (リフレクションのみのコンテキストに読み込むこともできます)。</span><span class="sxs-lookup"><span data-stu-id="a68c8-118">Because of this attribute, runtimes refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="a68c8-119">アセンブリに反映されるツールは、リフレクションのみで参照アセンブリを読み込む必要があります。それ以外の場合、ランタイムは <xref:System.BadImageFormatException> をスローします。</span><span class="sxs-lookup"><span data-stu-id="a68c8-119">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="a68c8-120">`-refout` オプションと [`-refonly`](refonly-compiler-option.md) オプションは同時に指定できません。</span><span class="sxs-lookup"><span data-stu-id="a68c8-120">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="a68c8-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a68c8-121">See also</span></span>

- [<span data-ttu-id="a68c8-122">/refonly</span><span class="sxs-lookup"><span data-stu-id="a68c8-122">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="a68c8-123">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="a68c8-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="a68c8-124">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="a68c8-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
