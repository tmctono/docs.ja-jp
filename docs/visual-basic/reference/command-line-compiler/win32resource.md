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
ms.openlocfilehash: 9351e9f6bcb7660dac2c49667ca8db6d578eff7c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834999"
---
# <a name="-win32resource"></a><span data-ttu-id="c4570-102">-win32resource</span><span class="sxs-lookup"><span data-stu-id="c4570-102">-win32resource</span></span>
<span data-ttu-id="c4570-103">出力ファイルには、Win32 リソース ファイルを挿入します。</span><span class="sxs-lookup"><span data-stu-id="c4570-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4570-104">構文</span><span class="sxs-lookup"><span data-stu-id="c4570-104">Syntax</span></span>  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="c4570-105">引数</span><span class="sxs-lookup"><span data-stu-id="c4570-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="c4570-106">出力ファイルに追加するリソース ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="c4570-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="c4570-107">ファイル名を引用符で囲みます ("")、スペースが含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="c4570-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4570-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="c4570-108">Remarks</span></span>  
 <span data-ttu-id="c4570-109">Microsoft Windows リソース コンパイラ (RC) では、Win32 リソース ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c4570-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="c4570-110">Win32 リソースは、バージョンを含めることができますか役立つビットマップ (アイコン) 情報でアプリケーションを識別する**ファイル エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="c4570-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="c4570-111">指定しない場合`-win32resource`コンパイラがアセンブリのバージョンに基づいてバージョン情報を生成します。</span><span class="sxs-lookup"><span data-stu-id="c4570-111">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="c4570-112">`-win32resource`と`-win32icon`オプションは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="c4570-112">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="c4570-113">参照してください[-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)参照に、[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]リソース ファイル、または[-リソース (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)をアタッチする、[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]リソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="c4570-113">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4570-114">`-win32resource`オプションは、Visual Studio 開発環境内からは使用できません。 コマンドラインからコンパイルする場合にのみ使用可能なです。</span><span class="sxs-lookup"><span data-stu-id="c4570-114">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4570-115">例</span><span class="sxs-lookup"><span data-stu-id="c4570-115">Example</span></span>  
 <span data-ttu-id="c4570-116">次のコードのコンパイル`In.vb`、Win32 リソース ファイルをアタッチします`Rf.res`:</span><span class="sxs-lookup"><span data-stu-id="c4570-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4570-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4570-117">See also</span></span>

- [<span data-ttu-id="c4570-118">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="c4570-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="c4570-119">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="c4570-119">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
