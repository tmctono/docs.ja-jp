---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 2de5fe82f1969a2fdb305d45951d7d698252c0c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61839223"
---
# <a name="-addmodule"></a><span data-ttu-id="2dee6-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="2dee6-102">-addmodule</span></span>
<span data-ttu-id="2dee6-103">指定ファイル内のすべての型情報を現在のコンパイル対象のプロジェクトで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2dee6-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dee6-104">構文</span><span class="sxs-lookup"><span data-stu-id="2dee6-104">Syntax</span></span>  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="2dee6-105">引数</span><span class="sxs-lookup"><span data-stu-id="2dee6-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="2dee6-106">必須。</span><span class="sxs-lookup"><span data-stu-id="2dee6-106">Required.</span></span> <span data-ttu-id="2dee6-107">メタデータが含まれますが、アセンブリ マニフェストが含まれていないファイルのコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="2dee6-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="2dee6-108">空白を含むファイル名を引用符で囲む必要があります ("")。</span><span class="sxs-lookup"><span data-stu-id="2dee6-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2dee6-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="2dee6-109">Remarks</span></span>  
 <span data-ttu-id="2dee6-110">によって示されているファイル、`fileList`パラメーターを使って作成する必要があります、`-target:module`オプション、または別のコンパイラと同じ`-target:module`します。</span><span class="sxs-lookup"><span data-stu-id="2dee6-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="2dee6-111">追加したすべてのモジュール`-addmodule`実行時に出力ファイルと同じディレクトリにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dee6-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="2dee6-112">つまり、コンパイル時に、任意のディレクトリにモジュールを指定することができますが、モジュールは実行時にアプリケーション ディレクトリに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dee6-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="2dee6-113">そうでない場合、<xref:System.TypeLoadException>エラー。</span><span class="sxs-lookup"><span data-stu-id="2dee6-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="2dee6-114">(暗黙的または明示的に) を指定する場合、[-ターゲット (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)以外のオプション`-target:module`で`-addmodule`に渡すファイル`-addmodule`プロジェクトのアセンブリの一部になります。</span><span class="sxs-lookup"><span data-stu-id="2dee6-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="2dee6-115">アセンブリがいずれかを含む出力ファイルを実行するために必要なまたは以上のファイルが追加で`-addmodule`します。</span><span class="sxs-lookup"><span data-stu-id="2dee6-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="2dee6-116">使用[/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)アセンブリを含むファイルからメタデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="2dee6-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2dee6-117">`-addmodule`オプションは、Visual Studio 開発環境内からは使用できません。 コマンドラインからコンパイルする場合にのみ使用可能なです。</span><span class="sxs-lookup"><span data-stu-id="2dee6-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2dee6-118">例</span><span class="sxs-lookup"><span data-stu-id="2dee6-118">Example</span></span>  
 <span data-ttu-id="2dee6-119">次のコードでは、モジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="2dee6-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="2dee6-120">次のコードでは、モジュールの型をインポートします。</span><span class="sxs-lookup"><span data-stu-id="2dee6-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="2dee6-121">実行すると`t1`、出力`802`します。</span><span class="sxs-lookup"><span data-stu-id="2dee6-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dee6-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="2dee6-122">See also</span></span>

- [<span data-ttu-id="2dee6-123">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="2dee6-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2dee6-124">-ターゲット (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2dee6-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="2dee6-125">-参照 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2dee6-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="2dee6-126">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="2dee6-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
