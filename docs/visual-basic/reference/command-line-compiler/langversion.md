---
title: -langversion
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 271606ac021e6afcb28fdac3e1bc86e1aaba7d2b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408539"
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="4f447-102">-langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f447-102">-langversion (Visual Basic)</span></span>
<span data-ttu-id="4f447-103">コンパイラで、指定した Visual Basic 言語バージョンに含まれている構文のみが受け入れられるようにします。</span><span class="sxs-lookup"><span data-stu-id="4f447-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f447-104">構文</span><span class="sxs-lookup"><span data-stu-id="4f447-104">Syntax</span></span>  
  
```console  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="4f447-105">引数</span><span class="sxs-lookup"><span data-stu-id="4f447-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="4f447-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="4f447-106">Required.</span></span> <span data-ttu-id="4f447-107">コンパイル中に使用される言語バージョン。</span><span class="sxs-lookup"><span data-stu-id="4f447-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="4f447-108">指定できる値は、`9`、`10`、`11`、`12`、`14`、`15`、`15.3`、`15.5`、`default`、`latest` です。</span><span class="sxs-lookup"><span data-stu-id="4f447-108">Accepted values are `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` and `latest`.</span></span>

 <span data-ttu-id="4f447-109">`.0` をマイナー バージョンとして使用して、整数値を指定することもできます (`11.0` など)。</span><span class="sxs-lookup"><span data-stu-id="4f447-109">Any of the whole numbers may also be specified using `.0` as the minor version, for example, `11.0`.</span></span>

 <span data-ttu-id="4f447-110">使用可能なすべての値の一覧を表示するには、コマンド ラインで `-langversion:?` を指定します。</span><span class="sxs-lookup"><span data-stu-id="4f447-110">You can see the list of all possible values by specifying `-langversion:?` on the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f447-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="4f447-111">Remarks</span></span>  
 <span data-ttu-id="4f447-112">`-langversion` オプションは、コンパイラで受け入れられる構文を指定します。</span><span class="sxs-lookup"><span data-stu-id="4f447-112">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="4f447-113">たとえば、言語バージョンが 9.0 であることを指定した場合、コンパイラではバージョン 10.0 以降でのみ有効な構文に対してエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="4f447-113">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="4f447-114">このオプションは、異なるバージョンの .NET Framework をターゲットとするアプリケーションを開発する場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f447-114">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="4f447-115">たとえば、.NET Framework 3.5 をターゲットとしている場合は、このオプションを使用して、言語バージョン 10.0 の構文を確実に使用しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4f447-115">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="4f447-116">`-langversion` を直接設定するには、コマンド ラインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f447-116">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="4f447-117">詳細については、「[対象となる特定の .NET Framework のバージョンの指定](/visualstudio/ide/visual-studio-multi-targeting-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f447-117">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/visual-studio-multi-targeting-overview).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f447-118">例</span><span class="sxs-lookup"><span data-stu-id="4f447-118">Example</span></span>  
 <span data-ttu-id="4f447-119">次のコードでは、Visual Basic 9.0 の `sample.vb` がコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="4f447-119">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f447-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f447-120">See also</span></span>

- [<span data-ttu-id="4f447-121">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="4f447-121">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="4f447-122">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="4f447-122">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="4f447-123">対象となる特定の .NET Framework バージョンの指定</span><span class="sxs-lookup"><span data-stu-id="4f447-123">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/visual-studio-multi-targeting-overview)
