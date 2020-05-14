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
ms.openlocfilehash: cee06adec89aac4b3e3f170df3bf932e466f3070
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004963"
---
# <a name="-win32resource"></a><span data-ttu-id="7038c-102">-win32resource</span><span class="sxs-lookup"><span data-stu-id="7038c-102">-win32resource</span></span>
<span data-ttu-id="7038c-103">Win32 リソース ファイルを出力ファイルに挿入します。</span><span class="sxs-lookup"><span data-stu-id="7038c-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7038c-104">構文</span><span class="sxs-lookup"><span data-stu-id="7038c-104">Syntax</span></span>  
  
```console  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="7038c-105">引数</span><span class="sxs-lookup"><span data-stu-id="7038c-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="7038c-106">出力ファイルに追加するリソース ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="7038c-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="7038c-107">ファイル名に空白が含まれている場合は、名前を二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="7038c-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7038c-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="7038c-108">Remarks</span></span>  
 <span data-ttu-id="7038c-109">Win32 リソース ファイルは、Microsoft Windows リソース コンパイラ (RC) を使用して作成することができます。</span><span class="sxs-lookup"><span data-stu-id="7038c-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="7038c-110">Win32 リソースは、バージョンまたはビットマップ (アイコン) 情報を格納することができ、**エクスプローラー**でアプリケーションを識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7038c-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="7038c-111">`-win32resource` を指定しない場合、コンパイラでアセンブリ バージョンに基づいてバージョン情報が生成されます。</span><span class="sxs-lookup"><span data-stu-id="7038c-111">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="7038c-112">`-win32resource` オプションと `-win32icon` オプションは同時に指定できません。</span><span class="sxs-lookup"><span data-stu-id="7038c-112">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="7038c-113">.NET Framework リソース ファイルの参照については「[-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)」を、.NET Framework リソース ファイルのアタッチについては「[-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7038c-113">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a .NET Framework resource file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7038c-114">`-win32resource` オプションは、Visual Studio 開発環境からは利用できません。これはコマンド ラインからコンパイルするときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7038c-114">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7038c-115">例</span><span class="sxs-lookup"><span data-stu-id="7038c-115">Example</span></span>  
 <span data-ttu-id="7038c-116">次のコードでは `In.vb` がコンパイルされ、Win32 リソース ファイル `Rf.res` がアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="7038c-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7038c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="7038c-117">See also</span></span>

- [<span data-ttu-id="7038c-118">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="7038c-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7038c-119">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="7038c-119">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
