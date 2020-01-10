---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: 9a5822a097828f818da020735c3822e86eb3236b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716636"
---
# <a name="-libpath"></a><span data-ttu-id="114c7-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="114c7-102">-libpath</span></span>
<span data-ttu-id="114c7-103">参照アセンブリの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="114c7-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="114c7-104">構文</span><span class="sxs-lookup"><span data-stu-id="114c7-104">Syntax</span></span>  
  
```console  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="114c7-105">引数</span><span class="sxs-lookup"><span data-stu-id="114c7-105">Arguments</span></span>  
  
|<span data-ttu-id="114c7-106">用語</span><span class="sxs-lookup"><span data-stu-id="114c7-106">Term</span></span>|<span data-ttu-id="114c7-107">Definition</span><span class="sxs-lookup"><span data-stu-id="114c7-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="114c7-108">必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="114c7-108">Required.</span></span> <span data-ttu-id="114c7-109">現在の作業ディレクトリ (コンパイラの呼び出し元のディレクトリ) または共通言語ランタイムのシステムディレクトリのいずれかで参照されているアセンブリが見つからない場合に、コンパイラが検索するディレクトリのセミコロン区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="114c7-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="114c7-110">ディレクトリ名にスペースが含まれている場合は、名前を引用符 ("") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="114c7-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="114c7-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="114c7-111">Remarks</span></span>  
 <span data-ttu-id="114c7-112">`-libpath` オプションは、 [-reference](../../../visual-basic/reference/command-line-compiler/reference.md)オプションによって参照されるアセンブリの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="114c7-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="114c7-113">コンパイラは、完全に修飾されていないアセンブリ参照を次の順序で検索します。</span><span class="sxs-lookup"><span data-stu-id="114c7-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1. <span data-ttu-id="114c7-114">現在の作業ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="114c7-114">Current working directory.</span></span> <span data-ttu-id="114c7-115">これは、コンパイラを起動したディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="114c7-115">This is the directory from which the compiler is invoked.</span></span>  
  
2. <span data-ttu-id="114c7-116">共通言語ランタイムのシステム ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="114c7-116">The common language runtime system directory.</span></span>  
  
3. <span data-ttu-id="114c7-117">`-libpath`によって指定されたディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="114c7-117">Directories specified by `-libpath`.</span></span>  
  
4. <span data-ttu-id="114c7-118">LIB 環境変数によって指定されているディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="114c7-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="114c7-119">`-libpath` オプションは加法です。これを複数回指定すると、前の値が追加されます。</span><span class="sxs-lookup"><span data-stu-id="114c7-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="114c7-120">アセンブリ参照を指定するには、`-reference` を使用します。</span><span class="sxs-lookup"><span data-stu-id="114c7-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="114c7-121">Visual Studio 統合開発環境で libpath を設定するには</span><span class="sxs-lookup"><span data-stu-id="114c7-121">To set -libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="114c7-122">1.**ソリューションエクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="114c7-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="114c7-123">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="114c7-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="114c7-124">2. **[参照]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="114c7-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="114c7-125">3. **[参照パス...]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="114c7-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="114c7-126">4. **[参照パス]** ダイアログボックスの **[フォルダー:]** ボックスにディレクトリ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="114c7-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="114c7-127">5. **[フォルダーの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="114c7-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="114c7-128">使用例</span><span class="sxs-lookup"><span data-stu-id="114c7-128">Example</span></span>  
 <span data-ttu-id="114c7-129">次のコードでは、`T2.vb` をコンパイルして .exe ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="114c7-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="114c7-130">コンパイラは、作業ディレクトリ、C: ドライブのルートディレクトリ、およびアセンブリ参照の C: ドライブの新しい Assemblies ディレクトリ内を検索します。</span><span class="sxs-lookup"><span data-stu-id="114c7-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="114c7-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="114c7-131">See also</span></span>

- [<span data-ttu-id="114c7-132">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="114c7-132">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="114c7-133">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="114c7-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="114c7-134">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="114c7-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
