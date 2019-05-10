---
title: -vbruntime
ms.date: 03/13/2018
f1_keywords:
- vbruntime
- -vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
ms.openlocfilehash: 56ea692d6e65d94c497fbc9406e03b40648c55a2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663492"
---
# <a name="-vbruntime"></a><span data-ttu-id="95f45-102">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="95f45-102">-vbruntime</span></span>
<span data-ttu-id="95f45-103">コンパイラが Visual Basic Runtime Library を参照せずにコンパイルするか、特定のランタイム ライブラリを参照してコンパイルするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="95f45-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95f45-104">構文</span><span class="sxs-lookup"><span data-stu-id="95f45-104">Syntax</span></span>  
  
```  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="95f45-105">引数</span><span class="sxs-lookup"><span data-stu-id="95f45-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="95f45-106">Visual Basic ランタイム ライブラリへの参照なしでコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="95f45-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="95f45-107">既定の Visual Basic ランタイム ライブラリへの参照を使用してコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="95f45-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="95f45-108">Visual Basic ランタイム ライブラリへの参照なしでコンパイルされ、アセンブリに、Visual Basic ランタイム ライブラリからのコア機能を埋め込みます。</span><span class="sxs-lookup"><span data-stu-id="95f45-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="95f45-109">指定したライブラリ (DLL) への参照を使用してコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="95f45-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95f45-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="95f45-110">Remarks</span></span>  
 <span data-ttu-id="95f45-111">`-vbruntime`コンパイラ オプションでは、コンパイラが、Visual Basic ランタイム ライブラリへの参照しないでコンパイルされていることを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="95f45-111">The `-vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="95f45-112">Visual Basic ランタイム ライブラリを参照しないでコンパイルする場合は、エラーまたは警告が Visual Basic ランタイム ヘルパーへの呼び出しを生成するコードまたは言語の構造に記録されます。</span><span class="sxs-lookup"><span data-stu-id="95f45-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="95f45-113">(A *Visual Basic ランタイム ヘルパー*特定言語のセマンティックを実行する実行時に呼び出される Microsoft.VisualBasic.dll で定義されている関数です)。</span><span class="sxs-lookup"><span data-stu-id="95f45-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="95f45-114">`-vbruntime+`オプションがない場合に発生するのと同じ動作を生成`-vbruntime`スイッチを指定します。</span><span class="sxs-lookup"><span data-stu-id="95f45-114">The `-vbruntime+` option produces the same behavior that occurs if no `-vbruntime` switch is specified.</span></span> <span data-ttu-id="95f45-115">使用することができます、`-vbruntime+`前をオーバーライドするオプション`-vbruntime`スイッチ。</span><span class="sxs-lookup"><span data-stu-id="95f45-115">You can use the `-vbruntime+` option to override previous `-vbruntime` switches.</span></span>  
  
 <span data-ttu-id="95f45-116">ほとんどのオブジェクトの`My`型は、使用する場合は使用できません、`-vbruntime-`または`-vbruntime:path`オプション。</span><span class="sxs-lookup"><span data-stu-id="95f45-116">Most objects of the `My` type are unavailable when you use the `-vbruntime-` or `-vbruntime:path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="95f45-117">Visual Basic ランタイムのコア機能の埋め込み</span><span class="sxs-lookup"><span data-stu-id="95f45-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="95f45-118">`-vbruntime*`オプションでは、ランタイム ライブラリへの参照なしでコンパイルすることができます。</span><span class="sxs-lookup"><span data-stu-id="95f45-118">The `-vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="95f45-119">代わりに、Visual Basic ランタイム ライブラリからのコア機能は、ユーザー アセンブリに埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="95f45-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="95f45-120">Visual Basic ランタイムが含まれていないプラットフォームでアプリケーションを実行している場合は、このオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="95f45-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="95f45-121">次のランタイムのメンバーが埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="95f45-121">The following runtime members are embedded:</span></span>  
  
- <span data-ttu-id="95f45-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> クラス</span><span class="sxs-lookup"><span data-stu-id="95f45-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
- <span data-ttu-id="95f45-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> メソッド</span><span class="sxs-lookup"><span data-stu-id="95f45-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
- <span data-ttu-id="95f45-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> メソッド</span><span class="sxs-lookup"><span data-stu-id="95f45-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
- <span data-ttu-id="95f45-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> メソッド</span><span class="sxs-lookup"><span data-stu-id="95f45-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
- <span data-ttu-id="95f45-126"><xref:Microsoft.VisualBasic.Constants.vbBack> 定数</span><span class="sxs-lookup"><span data-stu-id="95f45-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
- <span data-ttu-id="95f45-127"><xref:Microsoft.VisualBasic.Constants.vbCr> 定数</span><span class="sxs-lookup"><span data-stu-id="95f45-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
- <span data-ttu-id="95f45-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> 定数</span><span class="sxs-lookup"><span data-stu-id="95f45-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
- <span data-ttu-id="95f45-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> 定数</span><span class="sxs-lookup"><span data-stu-id="95f45-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
- <span data-ttu-id="95f45-130"><xref:Microsoft.VisualBasic.Constants.vbLf> 定数</span><span class="sxs-lookup"><span data-stu-id="95f45-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
- <span data-ttu-id="95f45-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> 定数</span><span class="sxs-lookup"><span data-stu-id="95f45-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
- <span data-ttu-id="95f45-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> 定数</span><span class="sxs-lookup"><span data-stu-id="95f45-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
- <span data-ttu-id="95f45-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> 定数</span><span class="sxs-lookup"><span data-stu-id="95f45-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
- <span data-ttu-id="95f45-134"><xref:Microsoft.VisualBasic.Constants.vbTab> 定数</span><span class="sxs-lookup"><span data-stu-id="95f45-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
- <span data-ttu-id="95f45-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> 定数</span><span class="sxs-lookup"><span data-stu-id="95f45-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
- <span data-ttu-id="95f45-136">一部のオブジェクトの`My`型</span><span class="sxs-lookup"><span data-stu-id="95f45-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="95f45-137">使用してコンパイルする場合、`-vbruntime*`オプションと、コードは、コア機能に埋め込まれていない Visual Basic ランタイム ライブラリからメンバーを参照、コンパイラには、メンバーが使用できないことを示すエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="95f45-137">If you compile using the `-vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="95f45-138">指定したライブラリを参照します。</span><span class="sxs-lookup"><span data-stu-id="95f45-138">Referencing a specified library</span></span>  
 <span data-ttu-id="95f45-139">使用することができます、 `path` Visual Basic ランタイム ライブラリの既定ではなくカスタム ランタイム ライブラリへの参照を使用してコンパイルする引数。</span><span class="sxs-lookup"><span data-stu-id="95f45-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="95f45-140">場合の値、`path`引数は、DLL への完全修飾パスがある場合、コンパイラでは、そのファイルは、ランタイム ライブラリとして使用します。</span><span class="sxs-lookup"><span data-stu-id="95f45-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="95f45-141">場合の値、 `path` DLL への完全修飾パス引数が、現在のフォルダーで識別された DLL を Visual Basic コンパイラがまず検索します。</span><span class="sxs-lookup"><span data-stu-id="95f45-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="95f45-142">使用して指定したパスを検索し、 [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)コンパイラ オプション。</span><span class="sxs-lookup"><span data-stu-id="95f45-142">It will then search in the path that you have specified by using the [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="95f45-143">場合、`-sdkpath`コンパイラ オプションが使用されない場合、コンパイラは、.NET Framework フォルダーで識別された DLL の検索 (`%systemroot%\Microsoft.NET\Framework\versionNumber`)。</span><span class="sxs-lookup"><span data-stu-id="95f45-143">If the `-sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="95f45-144">例</span><span class="sxs-lookup"><span data-stu-id="95f45-144">Example</span></span>  
 <span data-ttu-id="95f45-145">次の例は、使用する方法を示します、`-vbruntime`カスタム ライブラリへの参照を使用してコンパイルするにはオプションです。</span><span class="sxs-lookup"><span data-stu-id="95f45-145">The following example shows how to use the `-vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="95f45-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="95f45-146">See also</span></span>

- [<span data-ttu-id="95f45-147">Visual Basic Core-Visual Studio 2010 SP1 での新しいコンパイル モード</span><span class="sxs-lookup"><span data-stu-id="95f45-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [<span data-ttu-id="95f45-148">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="95f45-148">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="95f45-149">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="95f45-149">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="95f45-150">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="95f45-150">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
