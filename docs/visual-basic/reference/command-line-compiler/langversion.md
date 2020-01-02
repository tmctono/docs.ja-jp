---
title: -langversion
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 72a5638a5c5364381ffd68604b0d44830d53f365
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344212"
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="6d998-102">-langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6d998-102">-langversion (Visual Basic)</span></span>
<span data-ttu-id="6d998-103">指定された Visual Basic 言語バージョンに含まれている構文のみをコンパイラが受け入れるようにします。</span><span class="sxs-lookup"><span data-stu-id="6d998-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d998-104">構文</span><span class="sxs-lookup"><span data-stu-id="6d998-104">Syntax</span></span>  
  
```console  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="6d998-105">引数</span><span class="sxs-lookup"><span data-stu-id="6d998-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="6d998-106">必須。</span><span class="sxs-lookup"><span data-stu-id="6d998-106">Required.</span></span> <span data-ttu-id="6d998-107">コンパイル中に使用される言語バージョン。</span><span class="sxs-lookup"><span data-stu-id="6d998-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="6d998-108">許容される値は、`9`、`10`、`11`、`12`、`14`、`15`、`15.3`、`15.5`、`default`、および `latest`です。</span><span class="sxs-lookup"><span data-stu-id="6d998-108">Accepted values are `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` and `latest`.</span></span>

 <span data-ttu-id="6d998-109">`.0` をマイナーバージョン (`11.0`など) として使用して、整数値を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6d998-109">Any of the whole numbers may also be specified using `.0` as the minor version, for example, `11.0`.</span></span>

 <span data-ttu-id="6d998-110">使用可能なすべての値の一覧を表示するには、コマンドラインで `-langversion:?` を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d998-110">You can see the list of all possible values by specifying `-langversion:?` on the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d998-111">コメント</span><span class="sxs-lookup"><span data-stu-id="6d998-111">Remarks</span></span>  
 <span data-ttu-id="6d998-112">`-langversion` オプションは、コンパイラが受け入れる構文を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d998-112">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="6d998-113">たとえば、言語バージョンが9.0 であることを指定した場合、コンパイラはバージョン10.0 以降でのみ有効な構文に対してエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="6d998-113">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="6d998-114">このオプションは、異なるバージョンの .NET Framework を対象とするアプリケーションを開発する場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="6d998-114">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="6d998-115">たとえば、.NET Framework 3.5 を対象としている場合は、このオプションを使用して、言語バージョン10.0 の構文を使用しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="6d998-115">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="6d998-116">`-langversion` を直接設定するには、コマンドラインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d998-116">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="6d998-117">詳細については、「[対象となる特定の .NET Framework のバージョンの指定](/visualstudio/ide/visual-studio-multi-targeting-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d998-117">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/visual-studio-multi-targeting-overview).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d998-118">例</span><span class="sxs-lookup"><span data-stu-id="6d998-118">Example</span></span>  
 <span data-ttu-id="6d998-119">次のコードは、Visual Basic 9.0 の `sample.vb` をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="6d998-119">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6d998-120">参照</span><span class="sxs-lookup"><span data-stu-id="6d998-120">See also</span></span>

- [<span data-ttu-id="6d998-121">Visual Basic コマンドラインコンパイラ</span><span class="sxs-lookup"><span data-stu-id="6d998-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6d998-122">コンパイルコマンドラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="6d998-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="6d998-123">対象となる特定の .NET Framework バージョンの指定</span><span class="sxs-lookup"><span data-stu-id="6d998-123">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/visual-studio-multi-targeting-overview)
