---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: db2cb1eb107973e9ce60ecb0d669c677d4fa2c51
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793958"
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="a7c3f-102">-langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7c3f-102">-langversion (Visual Basic)</span></span>
<span data-ttu-id="a7c3f-103">コンパイラで指定された Visual Basic 言語のバージョンに含まれている構文のみを受け入れるようにします。</span><span class="sxs-lookup"><span data-stu-id="a7c3f-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7c3f-104">構文</span><span class="sxs-lookup"><span data-stu-id="a7c3f-104">Syntax</span></span>  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="a7c3f-105">引数</span><span class="sxs-lookup"><span data-stu-id="a7c3f-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="a7c3f-106">必須。</span><span class="sxs-lookup"><span data-stu-id="a7c3f-106">Required.</span></span> <span data-ttu-id="a7c3f-107">コンパイル時に使用する言語バージョン。</span><span class="sxs-lookup"><span data-stu-id="a7c3f-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="a7c3f-108">許容値は`9`、 `10`、 `11`、 `12`、 `14`、 `15`、 `15.3`、 `15.5`、`default`と`latest`します。</span><span class="sxs-lookup"><span data-stu-id="a7c3f-108">Accepted values are `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` and `latest`.</span></span>

 <span data-ttu-id="a7c3f-109">整数のいずれかを指定するとを使用して`.0`マイナー バージョンとして`11.0`します。</span><span class="sxs-lookup"><span data-stu-id="a7c3f-109">Any of the whole numbers may also be specified using `.0` as the minor version, for example, `11.0`.</span></span>

 <span data-ttu-id="a7c3f-110">指定することで、使用可能なすべての値の一覧を表示できます`-langversion:?`コマンド行にします。</span><span class="sxs-lookup"><span data-stu-id="a7c3f-110">You can see the list of all possible values by specifying `-langversion:?` on the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7c3f-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="a7c3f-111">Remarks</span></span>  
 <span data-ttu-id="a7c3f-112">`-langversion`オプションは、コンパイラはどのような構文を指定します。</span><span class="sxs-lookup"><span data-stu-id="a7c3f-112">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="a7c3f-113">たとえば、言語バージョンが 9.0 であることを指定する場合、コンパイラは、バージョン 10.0 でのみ有効であり、以降は、構文エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="a7c3f-113">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="a7c3f-114">.NET Framework の異なるバージョンを対象アプリケーションを開発する際に、このオプションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a7c3f-114">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="a7c3f-115">たとえば、.NET Framework 3.5 をターゲットにする場合は、言語バージョン 10.0 から構文を使用しないようにする、このオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7c3f-115">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="a7c3f-116">設定できる`-langversion`直接、コマンドラインを使用してのみです。</span><span class="sxs-lookup"><span data-stu-id="a7c3f-116">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="a7c3f-117">詳細については、「[対象となる特定の .NET Framework のバージョンの指定](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7c3f-117">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7c3f-118">例</span><span class="sxs-lookup"><span data-stu-id="a7c3f-118">Example</span></span>  
 <span data-ttu-id="a7c3f-119">次のコードのコンパイル`sample.vb`Visual Basic 9.0 の。</span><span class="sxs-lookup"><span data-stu-id="a7c3f-119">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7c3f-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7c3f-120">See also</span></span>

- [<span data-ttu-id="a7c3f-121">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="a7c3f-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a7c3f-122">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="a7c3f-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="a7c3f-123">対象となる特定の .NET Framework バージョンの指定</span><span class="sxs-lookup"><span data-stu-id="a7c3f-123">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
