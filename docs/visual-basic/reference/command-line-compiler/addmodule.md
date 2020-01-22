---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: dd98b45d75ff421dc81666ed47695132a49bfa3a
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524482"
---
# <a name="-addmodule"></a><span data-ttu-id="86a5b-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="86a5b-102">-addmodule</span></span>
<span data-ttu-id="86a5b-103">指定ファイル内のすべての型情報を現在のコンパイル対象のプロジェクトで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="86a5b-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86a5b-104">構文</span><span class="sxs-lookup"><span data-stu-id="86a5b-104">Syntax</span></span>  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="86a5b-105">引数</span><span class="sxs-lookup"><span data-stu-id="86a5b-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="86a5b-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="86a5b-106">Required.</span></span> <span data-ttu-id="86a5b-107">メタデータが含まれているものの、アセンブリマニフェストが含まれていないファイルのコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="86a5b-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="86a5b-108">スペースを含むファイル名は引用符 ("") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="86a5b-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86a5b-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="86a5b-109">Remarks</span></span>  
 <span data-ttu-id="86a5b-110">@No__t_0 パラメーターによって指定されたファイルは、`-target:module` オプションを使用して作成するか、または `-target:module` に相当する別のコンパイラを使用して作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86a5b-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="86a5b-111">@No__t_0 で追加されるすべてのモジュールは、実行時に出力ファイルと同じディレクトリに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86a5b-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="86a5b-112">つまり、コンパイル時に任意のディレクトリにモジュールを指定できますが、モジュールは実行時にアプリケーションディレクトリに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86a5b-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="86a5b-113">そうでない場合は、<xref:System.TypeLoadException> エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="86a5b-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="86a5b-114">@No__t_2 で `-target:module` 以外の[ターゲット (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)オプションを (暗黙的または明示的に) 指定すると、`-addmodule` に渡すファイルはプロジェクトのアセンブリの一部になります。</span><span class="sxs-lookup"><span data-stu-id="86a5b-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="86a5b-115">@No__t_0 で追加された1つ以上のファイルを含む出力ファイルを実行するには、アセンブリが必要です。</span><span class="sxs-lookup"><span data-stu-id="86a5b-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="86a5b-116">アセンブリを含むファイルからメタデータをインポートするには、[-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="86a5b-116">Use [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="86a5b-117">@No__t_0 オプションは、Visual Studio 開発環境内からは使用できません。これは、コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="86a5b-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86a5b-118">例</span><span class="sxs-lookup"><span data-stu-id="86a5b-118">Example</span></span>  
 <span data-ttu-id="86a5b-119">次のコードでは、モジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="86a5b-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="86a5b-120">次のコードは、モジュールの型をインポートします。</span><span class="sxs-lookup"><span data-stu-id="86a5b-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="86a5b-121">`t1` を実行すると、`802` が出力されます。</span><span class="sxs-lookup"><span data-stu-id="86a5b-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86a5b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="86a5b-122">See also</span></span>

- [<span data-ttu-id="86a5b-123">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="86a5b-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="86a5b-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86a5b-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="86a5b-125">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86a5b-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="86a5b-126">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="86a5b-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
