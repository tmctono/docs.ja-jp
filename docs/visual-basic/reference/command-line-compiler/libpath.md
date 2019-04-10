---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: b7bfcb0f2034145822922126fe61efea8d8ef269
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344209"
---
# <a name="-libpath"></a><span data-ttu-id="30697-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="30697-102">-libpath</span></span>
<span data-ttu-id="30697-103">参照先アセンブリの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="30697-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30697-104">構文</span><span class="sxs-lookup"><span data-stu-id="30697-104">Syntax</span></span>  
  
```  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="30697-105">引数</span><span class="sxs-lookup"><span data-stu-id="30697-105">Arguments</span></span>  
  
|<span data-ttu-id="30697-106">用語</span><span class="sxs-lookup"><span data-stu-id="30697-106">Term</span></span>|<span data-ttu-id="30697-107">定義</span><span class="sxs-lookup"><span data-stu-id="30697-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="30697-108">必須。</span><span class="sxs-lookup"><span data-stu-id="30697-108">Required.</span></span> <span data-ttu-id="30697-109">場合に参照アセンブリを検索するコンパイラ用のディレクトリのセミコロン区切りのリストに含まれていないか、現在の作業ディレクトリ (コンパイラの起動元のディレクトリ) または共通言語ランタイムのシステム ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="30697-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="30697-110">ディレクトリ名にスペースが含まれている場合は、名前を引用符で囲みます ("")。</span><span class="sxs-lookup"><span data-stu-id="30697-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30697-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="30697-111">Remarks</span></span>  
 <span data-ttu-id="30697-112">`-libpath`オプションによって参照されるアセンブリの場所を指定する、 [-参照](../../../visual-basic/reference/command-line-compiler/reference.md)オプション。</span><span class="sxs-lookup"><span data-stu-id="30697-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="30697-113">コンパイラは、完全に修飾されていないアセンブリ参照を次の順序で検索します。</span><span class="sxs-lookup"><span data-stu-id="30697-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1. <span data-ttu-id="30697-114">現在の作業ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="30697-114">Current working directory.</span></span> <span data-ttu-id="30697-115">これは、コンパイラを起動したディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="30697-115">This is the directory from which the compiler is invoked.</span></span>  
  
2. <span data-ttu-id="30697-116">共通言語ランタイムのシステム ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="30697-116">The common language runtime system directory.</span></span>  
  
3. <span data-ttu-id="30697-117">によって指定されたディレクトリ`/libpath`します。</span><span class="sxs-lookup"><span data-stu-id="30697-117">Directories specified by `/libpath`.</span></span>  
  
4. <span data-ttu-id="30697-118">LIB 環境変数によって指定されているディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="30697-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="30697-119">`-libpath`オプションが指定するには複数を指定すると、前の値に 1 回追加します。</span><span class="sxs-lookup"><span data-stu-id="30697-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="30697-120">使用`-reference`アセンブリ参照を指定します。</span><span class="sxs-lookup"><span data-stu-id="30697-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="30697-121">Visual Studio で/libpath を設定するのには、統合開発環境</span><span class="sxs-lookup"><span data-stu-id="30697-121">To set /libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="30697-122">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="30697-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="30697-123">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30697-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="30697-124">2.**[参照]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="30697-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="30697-125">3.をクリックして、**パスを参照しています.** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="30697-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="30697-126">4.**参照パス** ダイアログ ボックスで、ディレクトリ名を入力、**フォルダー:** ボックス。</span><span class="sxs-lookup"><span data-stu-id="30697-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="30697-127">5.クリックして**フォルダーの追加**します。</span><span class="sxs-lookup"><span data-stu-id="30697-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="30697-128">例</span><span class="sxs-lookup"><span data-stu-id="30697-128">Example</span></span>  
 <span data-ttu-id="30697-129">次のコードのコンパイル`T2.vb`.exe ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="30697-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="30697-130">コンパイラは、アセンブリ参照の作業ディレクトリ、c: ドライブのルート ディレクトリおよび c: ドライブの新しいアセンブリのディレクトリを検索します。</span><span class="sxs-lookup"><span data-stu-id="30697-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="30697-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="30697-131">See also</span></span>

- [<span data-ttu-id="30697-132">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="30697-132">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="30697-133">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="30697-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="30697-134">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="30697-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
