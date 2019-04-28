---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 4093e98738cf6e41cd450229d82e3672fe9687ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788870"
---
# <a name="-refonly-visual-basic"></a><span data-ttu-id="79dc6-102">-refonly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79dc6-102">-refonly (Visual Basic)</span></span>

<span data-ttu-id="79dc6-103">**-Refonly**オプションでは、コンパイルのプライマリ出力で実装アセンブリではなく、参照アセンブリがあることを示します。</span><span class="sxs-lookup"><span data-stu-id="79dc6-103">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="79dc6-104">`-refonly` パラメーターは、参照アセンブリを実行できない場合に、PDB の出力を暗黙的に無効にします。</span><span class="sxs-lookup"><span data-stu-id="79dc6-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="79dc6-105">構文</span><span class="sxs-lookup"><span data-stu-id="79dc6-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="79dc6-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="79dc6-106">Remarks</span></span>

<span data-ttu-id="79dc6-107">Visual Basic は、`-refout`バージョン 15.3 以降を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="79dc6-107">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="79dc6-108">参照アセンブリは、実装コードではなくメタデータが含まれているメタデータのみアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="79dc6-108">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="79dc6-109">匿名型を除くすべての型およびメンバーの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="79dc6-109">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="79dc6-110">(本体なしではなく) `throw null` 本体を使用する理由は、PEVerify を実行して渡せるようにするためです (そのためにメタデータの完全性を検証します)。</span><span class="sxs-lookup"><span data-stu-id="79dc6-110">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="79dc6-111">参照アセンブリは、アセンブリ レベル[ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute)属性。</span><span class="sxs-lookup"><span data-stu-id="79dc6-111">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="79dc6-112">この属性は、ソースで指定できます (指定すると、コンパイラではこれを合成する必要がなくなります)。</span><span class="sxs-lookup"><span data-stu-id="79dc6-112">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="79dc6-113">この属性により、ランタイムは、実行の参照アセンブリの読み込みが拒否されます (ただしリフレクション専用コンテキストに読み込まれていることがあります)。</span><span class="sxs-lookup"><span data-stu-id="79dc6-113">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="79dc6-114">アセンブリにリフレクションするツールは、リフレクション専用として参照アセンブリが読み込まれることを確認する必要があります。それ以外の場合、ランタイム、<xref:System.BadImageFormatException>します。</span><span class="sxs-lookup"><span data-stu-id="79dc6-114">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="79dc6-115">`-refonly` オプションと [`-refout`](refout-compiler-option.md) オプションは同時に指定できません。</span><span class="sxs-lookup"><span data-stu-id="79dc6-115">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="79dc6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="79dc6-116">See also</span></span>

- [<span data-ttu-id="79dc6-117">/refout</span><span class="sxs-lookup"><span data-stu-id="79dc6-117">-refout</span></span>](refout-compiler-option.md)
- [<span data-ttu-id="79dc6-118">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="79dc6-118">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="79dc6-119">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="79dc6-119">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
