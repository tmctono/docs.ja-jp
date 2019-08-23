---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 0e0915a2534f950cec074632a59750c3f96b679d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962456"
---
# <a name="-addmodule"></a><span data-ttu-id="94d47-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="94d47-102">-addmodule</span></span>
<span data-ttu-id="94d47-103">指定ファイル内のすべての型情報を現在のコンパイル対象のプロジェクトで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="94d47-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94d47-104">構文</span><span class="sxs-lookup"><span data-stu-id="94d47-104">Syntax</span></span>  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="94d47-105">引数</span><span class="sxs-lookup"><span data-stu-id="94d47-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="94d47-106">必須。</span><span class="sxs-lookup"><span data-stu-id="94d47-106">Required.</span></span> <span data-ttu-id="94d47-107">メタデータが含まれているものの、アセンブリマニフェストが含まれていないファイルのコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="94d47-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="94d47-108">スペースを含むファイル名は引用符 ("") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="94d47-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94d47-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="94d47-109">Remarks</span></span>  
 <span data-ttu-id="94d47-110">`fileList`パラメーターによって一覧表示されるファイルは、 `-target:module`オプションを使用して作成するか、 `-target:module`と同じ別のコンパイラを使用して作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94d47-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="94d47-111">で`-addmodule`追加されたすべてのモジュールは、実行時に出力ファイルと同じディレクトリに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94d47-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="94d47-112">つまり、コンパイル時に任意のディレクトリにモジュールを指定できますが、モジュールは実行時にアプリケーションディレクトリに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94d47-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="94d47-113">そうでない場合は、 <xref:System.TypeLoadException>エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="94d47-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="94d47-114">(暗黙的または明示的に) を指定した場合を除き`-target:module` `-addmodule`、[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)オプションを指定`-addmodule`すると、に渡すファイルはプロジェクトのアセンブリの一部になります。</span><span class="sxs-lookup"><span data-stu-id="94d47-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="94d47-115">アセンブリは、で`-addmodule`追加された1つ以上のファイルを含む出力ファイルを実行するために必要です。</span><span class="sxs-lookup"><span data-stu-id="94d47-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="94d47-116">アセンブリを含むファイルからメタデータをインポートするには、 [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="94d47-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="94d47-117">この`-addmodule`オプションは、Visual Studio 開発環境内からは使用できません。コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="94d47-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94d47-118">例</span><span class="sxs-lookup"><span data-stu-id="94d47-118">Example</span></span>  
 <span data-ttu-id="94d47-119">次のコードでは、モジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="94d47-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="94d47-120">次のコードは、モジュールの型をインポートします。</span><span class="sxs-lookup"><span data-stu-id="94d47-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="94d47-121">を実行`t1`すると、が`802`出力されます。</span><span class="sxs-lookup"><span data-stu-id="94d47-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94d47-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="94d47-122">See also</span></span>

- [<span data-ttu-id="94d47-123">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="94d47-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="94d47-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94d47-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="94d47-125">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94d47-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="94d47-126">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="94d47-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
