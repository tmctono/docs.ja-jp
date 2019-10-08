---
title: -sdkpath
ms.date: 07/20/2015
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
ms.openlocfilehash: 46cec7ac3cb78c4fc97e299535f9085eff6daeff
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004693"
---
# <a name="-sdkpath"></a><span data-ttu-id="77b68-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="77b68-102">-sdkpath</span></span>
<span data-ttu-id="77b68-103">Mscorlib.dll と、mscorlib.dll の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="77b68-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77b68-104">構文</span><span class="sxs-lookup"><span data-stu-id="77b68-104">Syntax</span></span>  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="77b68-105">引数</span><span class="sxs-lookup"><span data-stu-id="77b68-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="77b68-106">コンパイルに使用する mscorlib.dll と Microsoft のバージョンを格納しているディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="77b68-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="77b68-107">このパスは、読み込まれるまで検証されません。</span><span class="sxs-lookup"><span data-stu-id="77b68-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="77b68-108">スペースが含まれている場合は、ディレクトリ名を引用符 ("") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="77b68-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77b68-109">コメント</span><span class="sxs-lookup"><span data-stu-id="77b68-109">Remarks</span></span>  
 <span data-ttu-id="77b68-110">このオプションは、Visual Basic コンパイラに対して、既定以外の場所から mscorlib.dll ファイルと Microsoft ファイルの .dll ファイルを読み込むように指示します。</span><span class="sxs-lookup"><span data-stu-id="77b68-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="77b68-111">@No__t-0 オプションは、 [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)と共に使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="77b68-111">The `-sdkpath` option was designed to be used with [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="77b68-112">.NET Compact Framework では、これらのサポートライブラリのさまざまなバージョンを使用して、デバイスでは検出されない型と言語機能を使用しないようにしています。</span><span class="sxs-lookup"><span data-stu-id="77b68-112">The .NET Compact Framework uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="77b68-113">@No__t-0 オプションは、Visual Studio 開発環境内からは使用できません。これは、コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="77b68-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="77b68-114">@No__t-0 オプションは、Visual Basic デバイスプロジェクトが読み込まれるときに設定されます。</span><span class="sxs-lookup"><span data-stu-id="77b68-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="77b68-115">@No__t-0 コンパイラオプションを使用して、コンパイラが Visual Basic ランタイムライブラリへの参照を使用せずにコンパイルするように指定できます。</span><span class="sxs-lookup"><span data-stu-id="77b68-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="77b68-116">詳細については、「 [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77b68-116">For more information, see [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="77b68-117">例</span><span class="sxs-lookup"><span data-stu-id="77b68-117">Example</span></span>  
 <span data-ttu-id="77b68-118">次のコードでは、C ドライブの .NET Compact Framework の既定のインストールディレクトリにある Mscorlib.dll と Microsoft. .dll のバージョンを使用して、.NET Compact Framework と `Myfile.vb` がコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="77b68-118">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="77b68-119">通常は、最新バージョンの .NET Compact Framework を使用します。</span><span class="sxs-lookup"><span data-stu-id="77b68-119">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="77b68-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="77b68-120">See also</span></span>

- [<span data-ttu-id="77b68-121">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="77b68-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="77b68-122">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="77b68-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="77b68-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="77b68-123">-netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [<span data-ttu-id="77b68-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="77b68-124">-vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
