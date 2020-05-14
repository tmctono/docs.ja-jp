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
ms.openlocfilehash: 8c7789c6af7b82ecb40ecd73d09f64aa1da3fd4b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005060"
---
# <a name="-vbruntime"></a><span data-ttu-id="451a3-102">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="451a3-102">-vbruntime</span></span>
<span data-ttu-id="451a3-103">コンパイラが Visual Basic Runtime Library を参照せずにコンパイルするか、特定のランタイム ライブラリを参照してコンパイルするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="451a3-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="451a3-104">構文</span><span class="sxs-lookup"><span data-stu-id="451a3-104">Syntax</span></span>  
  
```console  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="451a3-105">引数</span><span class="sxs-lookup"><span data-stu-id="451a3-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="451a3-106">Visual Basic ランタイム ライブラリを参照せずにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="451a3-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="451a3-107">既定の Visual Basic ランタイム ライブラリを参照してコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="451a3-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="451a3-108">Visual Basic ランタイム ライブラリを参照せずにコンパイルし、Visual Basic ランタイム ライブラリからアセンブリにコア機能を埋め込みます。</span><span class="sxs-lookup"><span data-stu-id="451a3-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="451a3-109">指定したライブラリ (DLL) を参照してコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="451a3-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="451a3-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="451a3-110">Remarks</span></span>  
 <span data-ttu-id="451a3-111">`-vbruntime` コンパイラ オプションでは、コンパイラで Visual Basic ランタイム ライブラリを参照せずにコンパイルするように指定することができます。</span><span class="sxs-lookup"><span data-stu-id="451a3-111">The `-vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="451a3-112">Visual Basic ランタイム ライブラリを参照せずにコンパイルする場合、エラーまたは警告は、Visual Basic ランタイム ヘルパーの呼び出しを生成するコードまたは言語コンストラクトに記録されます</span><span class="sxs-lookup"><span data-stu-id="451a3-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="451a3-113">("*Visual Basic ランタイム ヘルパー*" は、特定の言語のセマンティックを実行するために実行時に呼び出される、Microsoft.VisualBasic.dll 内に定義された関数です)。</span><span class="sxs-lookup"><span data-stu-id="451a3-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="451a3-114">`-vbruntime+` オプションでは、`-vbruntime` スイッチが指定されていない場合に発生する動作と同じ動作が生成されます。</span><span class="sxs-lookup"><span data-stu-id="451a3-114">The `-vbruntime+` option produces the same behavior that occurs if no `-vbruntime` switch is specified.</span></span> <span data-ttu-id="451a3-115">`-vbruntime+` オプションを使用すると、それより前の `-vbruntime` スイッチをオーバーライドすることができます。</span><span class="sxs-lookup"><span data-stu-id="451a3-115">You can use the `-vbruntime+` option to override previous `-vbruntime` switches.</span></span>  
  
 <span data-ttu-id="451a3-116">`-vbruntime-` または `-vbruntime:path` オプションを使用する場合、`My` 型のほとんどのオブジェクトは使用できません。</span><span class="sxs-lookup"><span data-stu-id="451a3-116">Most objects of the `My` type are unavailable when you use the `-vbruntime-` or `-vbruntime:path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="451a3-117">Visual Basic ランタイム コア機能の埋め込み</span><span class="sxs-lookup"><span data-stu-id="451a3-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="451a3-118">`-vbruntime*` オプションを使用すると、ランタイム ライブラリを参照せずにコンパイルすることができます。</span><span class="sxs-lookup"><span data-stu-id="451a3-118">The `-vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="451a3-119">代わりに、Visual Basic ランタイム ライブラリのコア機能がユーザー アセンブリに埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="451a3-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="451a3-120">このオプションは、Visual Basic ランタイムを含まないプラットフォームでアプリケーションを実行する場合に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="451a3-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="451a3-121">次のランタイム メンバーが埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="451a3-121">The following runtime members are embedded:</span></span>  
  
- <span data-ttu-id="451a3-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> クラス</span><span class="sxs-lookup"><span data-stu-id="451a3-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
- <span data-ttu-id="451a3-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> メソッド</span><span class="sxs-lookup"><span data-stu-id="451a3-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
- <span data-ttu-id="451a3-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> メソッド</span><span class="sxs-lookup"><span data-stu-id="451a3-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
- <span data-ttu-id="451a3-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> メソッド</span><span class="sxs-lookup"><span data-stu-id="451a3-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
- <span data-ttu-id="451a3-126"><xref:Microsoft.VisualBasic.Constants.vbBack> 定数</span><span class="sxs-lookup"><span data-stu-id="451a3-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
- <span data-ttu-id="451a3-127"><xref:Microsoft.VisualBasic.Constants.vbCr> 定数</span><span class="sxs-lookup"><span data-stu-id="451a3-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
- <span data-ttu-id="451a3-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> 定数</span><span class="sxs-lookup"><span data-stu-id="451a3-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
- <span data-ttu-id="451a3-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> 定数</span><span class="sxs-lookup"><span data-stu-id="451a3-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
- <span data-ttu-id="451a3-130"><xref:Microsoft.VisualBasic.Constants.vbLf> 定数</span><span class="sxs-lookup"><span data-stu-id="451a3-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
- <span data-ttu-id="451a3-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> 定数</span><span class="sxs-lookup"><span data-stu-id="451a3-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
- <span data-ttu-id="451a3-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> 定数</span><span class="sxs-lookup"><span data-stu-id="451a3-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
- <span data-ttu-id="451a3-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> 定数</span><span class="sxs-lookup"><span data-stu-id="451a3-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
- <span data-ttu-id="451a3-134"><xref:Microsoft.VisualBasic.Constants.vbTab> 定数</span><span class="sxs-lookup"><span data-stu-id="451a3-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
- <span data-ttu-id="451a3-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> 定数</span><span class="sxs-lookup"><span data-stu-id="451a3-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
- <span data-ttu-id="451a3-136">`My` 型の一部のオブジェクト</span><span class="sxs-lookup"><span data-stu-id="451a3-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="451a3-137">`-vbruntime*` オプションを使用してコンパイルするときに、コア機能で埋め込まれない Visual Basic ランタイム ライブラリのメンバーをコードで参照している場合、そのメンバーが使用できないことを示すエラーがコンパイラから返されます。</span><span class="sxs-lookup"><span data-stu-id="451a3-137">If you compile using the `-vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="451a3-138">指定したライブラリの参照</span><span class="sxs-lookup"><span data-stu-id="451a3-138">Referencing a specified library</span></span>  
 <span data-ttu-id="451a3-139">`path` 引数を使用すると、既定の Visual Basic ランタイム ライブラリの代わりに、カスタム ランタイム ライブラリを参照してコンパイルすることができます。</span><span class="sxs-lookup"><span data-stu-id="451a3-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="451a3-140">`path` 引数の値が DLL への完全修飾パスである場合、そのファイルがコンパイラでランタイム ライブラリとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="451a3-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="451a3-141">`path` 引数の値が DLL への完全修飾パスではない場合、最初に現在のフォルダー内の指定した DLL が、Visual Basic コンパイラによって検索されます。</span><span class="sxs-lookup"><span data-stu-id="451a3-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="451a3-142">次に、[-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) コンパイラ オプションを使用して、指定したパスが検索されます。</span><span class="sxs-lookup"><span data-stu-id="451a3-142">It will then search in the path that you have specified by using the [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="451a3-143">`-sdkpath` コンパイラ オプションを使わない場合、指定した DLL がコンパイラによって、.NET Framework フォルダー (`%systemroot%\Microsoft.NET\Framework\versionNumber`) で検索されます。</span><span class="sxs-lookup"><span data-stu-id="451a3-143">If the `-sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="451a3-144">例</span><span class="sxs-lookup"><span data-stu-id="451a3-144">Example</span></span>  
 <span data-ttu-id="451a3-145">次の例は、`-vbruntime` オプションを使用して、カスタム ライブラリを参照してコンパイルする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="451a3-145">The following example shows how to use the `-vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="451a3-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="451a3-146">See also</span></span>

- [<span data-ttu-id="451a3-147">Visual Basic コア - Visual Studio 2010 SP1 の新しいコンパイル モード</span><span class="sxs-lookup"><span data-stu-id="451a3-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [<span data-ttu-id="451a3-148">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="451a3-148">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="451a3-149">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="451a3-149">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="451a3-150">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="451a3-150">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
