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
# <a name="-sdkpath"></a><span data-ttu-id="b30cd-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="b30cd-102">-sdkpath</span></span>
<span data-ttu-id="b30cd-103">Mscorlib.dll と Microsoft.VisualBasic.dll の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="b30cd-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b30cd-104">構文</span><span class="sxs-lookup"><span data-stu-id="b30cd-104">Syntax</span></span>  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="b30cd-105">引数</span><span class="sxs-lookup"><span data-stu-id="b30cd-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="b30cd-106">Mscorlib.dll および Microsoft.VisualBasic.dll のコンパイルに使用するバージョンを格納するディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="b30cd-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="b30cd-107">このパスは、読み込まれるまで検査されません。</span><span class="sxs-lookup"><span data-stu-id="b30cd-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="b30cd-108">ディレクトリ名に空白が含まれている場合は、文字列を二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="b30cd-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b30cd-109">コメント</span><span class="sxs-lookup"><span data-stu-id="b30cd-109">Remarks</span></span>  
 <span data-ttu-id="b30cd-110">このオプションは、Visual Basic コンパイラに対して、既定以外の場所から mscorlib.dll ファイルと Microsoft ファイルの .dll ファイルを読み込むように指示します。</span><span class="sxs-lookup"><span data-stu-id="b30cd-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="b30cd-111">@No__t-0 オプションは、 [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)と共に使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="b30cd-111">The `-sdkpath` option was designed to be used with [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="b30cd-112">.NET Compact Framework では、これらのサポートライブラリのさまざまなバージョンを使用して、デバイスでは検出されない型と言語機能を使用しないようにしています。</span><span class="sxs-lookup"><span data-stu-id="b30cd-112">The .NET Compact Framework uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b30cd-113">`-sdkpath` オプションは Visual Studio の開発環境内からは利用できません。このオプションを利用できるのは、コマンド ラインからコンパイルする場合のみです。</span><span class="sxs-lookup"><span data-stu-id="b30cd-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="b30cd-114">`-sdkpath` オプションは Visual Basic デバイス プロジェクトがロードされている場合に設定されます。</span><span class="sxs-lookup"><span data-stu-id="b30cd-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="b30cd-115">@No__t-0 コンパイラオプションを使用して、コンパイラが Visual Basic ランタイムライブラリへの参照を使用せずにコンパイルするように指定できます。</span><span class="sxs-lookup"><span data-stu-id="b30cd-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="b30cd-116">詳細については、「 [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b30cd-116">For more information, see [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b30cd-117">例</span><span class="sxs-lookup"><span data-stu-id="b30cd-117">Example</span></span>  
 <span data-ttu-id="b30cd-118">次のコードでは、C ドライブ上の .NET Compact Framework の既定のインストール ディレクトリにある Mscorlib.dll のバージョンとMicrosoft.VisualBasic.dll のバージョンを使用して、.NET Compact Framework で `Myfile.vb` をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="b30cd-118">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="b30cd-119">通常、最新のバージョンの .NET Compact Framework を使用します。</span><span class="sxs-lookup"><span data-stu-id="b30cd-119">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b30cd-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="b30cd-120">See also</span></span>

- [<span data-ttu-id="b30cd-121">Visual Basic コマンドラインコンパイラ</span><span class="sxs-lookup"><span data-stu-id="b30cd-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="b30cd-122">コンパイルコマンドラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="b30cd-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="b30cd-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="b30cd-123">-netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [<span data-ttu-id="b30cd-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="b30cd-124">-vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
