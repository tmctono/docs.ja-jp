---
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
ms.openlocfilehash: 382dcc6571aa06ecdfc32bf43080c4b7a36eb1f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961298"
---
# <a name="-win32resource"></a><span data-ttu-id="c002c-102">-win32resource</span><span class="sxs-lookup"><span data-stu-id="c002c-102">-win32resource</span></span>
<span data-ttu-id="c002c-103">Win32 リソースファイルを出力ファイルに挿入します。</span><span class="sxs-lookup"><span data-stu-id="c002c-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c002c-104">構文</span><span class="sxs-lookup"><span data-stu-id="c002c-104">Syntax</span></span>  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="c002c-105">引数</span><span class="sxs-lookup"><span data-stu-id="c002c-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="c002c-106">出力ファイルに追加するリソースファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="c002c-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="c002c-107">ファイル名にスペースが含まれている場合は、ファイル名を引用符 ("") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c002c-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c002c-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="c002c-108">Remarks</span></span>  
 <span data-ttu-id="c002c-109">Win32 リソースファイルは、Microsoft Windows リソースコンパイラ (RC) を使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="c002c-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="c002c-110">Win32 リソースには、**ファイルエクスプローラー**でアプリケーションを識別するのに役立つバージョンまたはビットマップ (アイコン) 情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c002c-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="c002c-111">を指定`-win32resource`しない場合、コンパイラはアセンブリのバージョンに基づいてバージョン情報を生成します。</span><span class="sxs-lookup"><span data-stu-id="c002c-111">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="c002c-112">オプション`-win32resource` と`-win32icon`オプションは同時に指定できません。</span><span class="sxs-lookup"><span data-stu-id="c002c-112">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="c002c-113">.NET Framework リソースファイルを参照する場合は[-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)を参照し、.NET Framework リソースファイルをアタッチする場合は[-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c002c-113">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a .NET Framework resource file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c002c-114">この`-win32resource`オプションは、Visual Studio 開発環境内からは使用できません。コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c002c-114">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c002c-115">例</span><span class="sxs-lookup"><span data-stu-id="c002c-115">Example</span></span>  
 <span data-ttu-id="c002c-116">次のコードは`In.vb` 、Win32 リソースファイルを`Rf.res`コンパイルしてアタッチします。</span><span class="sxs-lookup"><span data-stu-id="c002c-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c002c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c002c-117">See also</span></span>

- [<span data-ttu-id="c002c-118">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="c002c-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="c002c-119">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="c002c-119">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
