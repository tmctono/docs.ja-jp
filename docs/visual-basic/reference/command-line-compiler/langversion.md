---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 15f334f280c2aca83ba5b628a1137464c31c6282
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005556"
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="464c0-102">-langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="464c0-102">-langversion (Visual Basic)</span></span>
<span data-ttu-id="464c0-103">指定された Visual Basic 言語バージョンに含まれている構文のみをコンパイラが受け入れるようにします。</span><span class="sxs-lookup"><span data-stu-id="464c0-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="464c0-104">構文</span><span class="sxs-lookup"><span data-stu-id="464c0-104">Syntax</span></span>  
  
```console  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="464c0-105">引数</span><span class="sxs-lookup"><span data-stu-id="464c0-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="464c0-106">必須。</span><span class="sxs-lookup"><span data-stu-id="464c0-106">Required.</span></span> <span data-ttu-id="464c0-107">コンパイル中に使用される言語バージョン。</span><span class="sxs-lookup"><span data-stu-id="464c0-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="464c0-108">許容される値は @no__t 0、`10`、`11`、`12`、`14`、`15`、`15.3`、`15.5`、`default`、`latest` です。</span><span class="sxs-lookup"><span data-stu-id="464c0-108">Accepted values are `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` and `latest`.</span></span>

 <span data-ttu-id="464c0-109">すべての整数は、マイナーバージョンとして `.0` を使用して指定することもできます (例: `11.0`)。</span><span class="sxs-lookup"><span data-stu-id="464c0-109">Any of the whole numbers may also be specified using `.0` as the minor version, for example, `11.0`.</span></span>

 <span data-ttu-id="464c0-110">使用可能なすべての値の一覧を表示するには、コマンドラインで `-langversion:?` を指定します。</span><span class="sxs-lookup"><span data-stu-id="464c0-110">You can see the list of all possible values by specifying `-langversion:?` on the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="464c0-111">コメント</span><span class="sxs-lookup"><span data-stu-id="464c0-111">Remarks</span></span>  
 <span data-ttu-id="464c0-112">@No__t-0 オプションは、コンパイラが受け入れる構文を指定します。</span><span class="sxs-lookup"><span data-stu-id="464c0-112">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="464c0-113">たとえば、言語バージョンが9.0 であることを指定した場合、コンパイラはバージョン10.0 以降でのみ有効な構文に対してエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="464c0-113">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="464c0-114">このオプションは、異なるバージョンの .NET Framework を対象とするアプリケーションを開発する場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="464c0-114">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="464c0-115">たとえば、.NET Framework 3.5 を対象としている場合は、このオプションを使用して、言語バージョン10.0 の構文を使用しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="464c0-115">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="464c0-116">@No__t-0 は、コマンドラインを使用して直接設定できます。</span><span class="sxs-lookup"><span data-stu-id="464c0-116">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="464c0-117">詳細については、「[対象となる特定の .NET Framework のバージョンの指定](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="464c0-117">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span></span>  
  
## <a name="example"></a><span data-ttu-id="464c0-118">例</span><span class="sxs-lookup"><span data-stu-id="464c0-118">Example</span></span>  
 <span data-ttu-id="464c0-119">次のコードは、Visual Basic 9.0 に対して `sample.vb` をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="464c0-119">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="464c0-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="464c0-120">See also</span></span>

- [<span data-ttu-id="464c0-121">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="464c0-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="464c0-122">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="464c0-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="464c0-123">対象となる特定の .NET Framework バージョンの指定</span><span class="sxs-lookup"><span data-stu-id="464c0-123">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
