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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005060"
---
# <a name="-vbruntime"></a><span data-ttu-id="3ff6c-102">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="3ff6c-102">-vbruntime</span></span>
<span data-ttu-id="3ff6c-103">コンパイラが Visual Basic Runtime Library を参照せずにコンパイルするか、特定のランタイム ライブラリを参照してコンパイルするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ff6c-104">構文</span><span class="sxs-lookup"><span data-stu-id="3ff6c-104">Syntax</span></span>  
  
```console  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="3ff6c-105">引数</span><span class="sxs-lookup"><span data-stu-id="3ff6c-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="3ff6c-106">Visual Basic ランタイムライブラリへの参照を使用せずにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="3ff6c-107">既定の Visual Basic ランタイムライブラリへの参照を使用してコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="3ff6c-108">Visual Basic ランタイムライブラリへの参照を使用せずにコンパイルし、Visual Basic ランタイムライブラリからアセンブリにコア機能を埋め込みます。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="3ff6c-109">指定したライブラリ (DLL) への参照を使用してコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ff6c-110">コメント</span><span class="sxs-lookup"><span data-stu-id="3ff6c-110">Remarks</span></span>  
 <span data-ttu-id="3ff6c-111">`-vbruntime` コンパイラオプションを使用すると、コンパイラが Visual Basic ランタイムライブラリへの参照を使用せずにコンパイルするように指定できます。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-111">The `-vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="3ff6c-112">Visual Basic ランタイムライブラリへの参照を使用せずにコンパイルする場合、エラーまたは警告は、Visual Basic ランタイムヘルパーの呼び出しを生成するコードまたは言語コンストラクトに記録されます。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="3ff6c-113">( *Visual Basic ランタイムヘルパー*は、特定の言語のセマンティックを実行するために実行時に呼び出される、Microsoft によって定義される関数です)。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="3ff6c-114">`-vbruntime+` オプションは、`-vbruntime` スイッチが指定されていない場合に発生するのと同じ動作を生成します。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-114">The `-vbruntime+` option produces the same behavior that occurs if no `-vbruntime` switch is specified.</span></span> <span data-ttu-id="3ff6c-115">`-vbruntime+` オプションを使用して、前の `-vbruntime` スイッチを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-115">You can use the `-vbruntime+` option to override previous `-vbruntime` switches.</span></span>  
  
 <span data-ttu-id="3ff6c-116">`-vbruntime-` または `-vbruntime:path` オプションを使用する場合、`My` 型のほとんどのオブジェクトは使用できません。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-116">Most objects of the `My` type are unavailable when you use the `-vbruntime-` or `-vbruntime:path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="3ff6c-117">埋め込み Visual Basic ランタイムコア機能</span><span class="sxs-lookup"><span data-stu-id="3ff6c-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="3ff6c-118">`-vbruntime*` オプションを使用すると、ランタイムライブラリへの参照を使用せずにコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-118">The `-vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="3ff6c-119">代わりに、Visual Basic ランタイムライブラリのコア機能がユーザーアセンブリに埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="3ff6c-120">このオプションは、アプリケーションが Visual Basic ランタイムを含まないプラットフォームで実行されている場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="3ff6c-121">次のランタイムメンバーが埋め込まれています。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-121">The following runtime members are embedded:</span></span>  
  
- <span data-ttu-id="3ff6c-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> クラス</span><span class="sxs-lookup"><span data-stu-id="3ff6c-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
- <span data-ttu-id="3ff6c-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> メソッド</span><span class="sxs-lookup"><span data-stu-id="3ff6c-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
- <span data-ttu-id="3ff6c-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> メソッド</span><span class="sxs-lookup"><span data-stu-id="3ff6c-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
- <span data-ttu-id="3ff6c-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> メソッド</span><span class="sxs-lookup"><span data-stu-id="3ff6c-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
- <span data-ttu-id="3ff6c-126"><xref:Microsoft.VisualBasic.Constants.vbBack> 定数</span><span class="sxs-lookup"><span data-stu-id="3ff6c-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
- <span data-ttu-id="3ff6c-127"><xref:Microsoft.VisualBasic.Constants.vbCr> 定数</span><span class="sxs-lookup"><span data-stu-id="3ff6c-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
- <span data-ttu-id="3ff6c-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> 定数</span><span class="sxs-lookup"><span data-stu-id="3ff6c-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
- <span data-ttu-id="3ff6c-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> 定数</span><span class="sxs-lookup"><span data-stu-id="3ff6c-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
- <span data-ttu-id="3ff6c-130"><xref:Microsoft.VisualBasic.Constants.vbLf> 定数</span><span class="sxs-lookup"><span data-stu-id="3ff6c-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
- <span data-ttu-id="3ff6c-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> 定数</span><span class="sxs-lookup"><span data-stu-id="3ff6c-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
- <span data-ttu-id="3ff6c-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> 定数</span><span class="sxs-lookup"><span data-stu-id="3ff6c-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
- <span data-ttu-id="3ff6c-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> 定数</span><span class="sxs-lookup"><span data-stu-id="3ff6c-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
- <span data-ttu-id="3ff6c-134"><xref:Microsoft.VisualBasic.Constants.vbTab> 定数</span><span class="sxs-lookup"><span data-stu-id="3ff6c-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
- <span data-ttu-id="3ff6c-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> 定数</span><span class="sxs-lookup"><span data-stu-id="3ff6c-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
- <span data-ttu-id="3ff6c-136">`My` 型の一部のオブジェクト</span><span class="sxs-lookup"><span data-stu-id="3ff6c-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="3ff6c-137">`-vbruntime*` オプションを使用してコンパイルし、コードがコア機能に埋め込まれていない Visual Basic ランタイムライブラリからメンバーを参照している場合、コンパイラは、メンバーが使用できないことを示すエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-137">If you compile using the `-vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="3ff6c-138">指定したライブラリの参照</span><span class="sxs-lookup"><span data-stu-id="3ff6c-138">Referencing a specified library</span></span>  
 <span data-ttu-id="3ff6c-139">`path` 引数を使用すると、既定の Visual Basic ランタイムライブラリの代わりに、カスタムランタイムライブラリへの参照を使用してコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="3ff6c-140">`path` 引数の値が DLL への完全修飾パスの場合、コンパイラはそのファイルをランタイムライブラリとして使用します。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="3ff6c-141">`path` 引数の値が DLL への完全修飾パスではない場合、Visual Basic コンパイラは最初に現在のフォルダー内の特定の DLL を検索します。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="3ff6c-142">次に、 [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)コンパイラオプションを使用して、指定したパスを検索します。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-142">It will then search in the path that you have specified by using the [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="3ff6c-143">`-sdkpath` コンパイラオプションが使用されていない場合、コンパイラは、識別された DLL を .NET Framework フォルダー (`%systemroot%\Microsoft.NET\Framework\versionNumber`) で検索します。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-143">If the `-sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ff6c-144">例</span><span class="sxs-lookup"><span data-stu-id="3ff6c-144">Example</span></span>  
 <span data-ttu-id="3ff6c-145">次の例は、`-vbruntime` オプションを使用して、カスタムライブラリへの参照を使用してコンパイルする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3ff6c-145">The following example shows how to use the `-vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="3ff6c-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ff6c-146">See also</span></span>

- [<span data-ttu-id="3ff6c-147">Visual Basic Core – Visual Studio 2010 SP1 の新しいコンパイルモード</span><span class="sxs-lookup"><span data-stu-id="3ff6c-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [<span data-ttu-id="3ff6c-148">Visual Basic コマンドラインコンパイラ</span><span class="sxs-lookup"><span data-stu-id="3ff6c-148">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="3ff6c-149">コンパイルコマンドラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="3ff6c-149">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="3ff6c-150">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="3ff6c-150">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
