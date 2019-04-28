---
title: -除外 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 5dcf9dc5cc0987e965aba7fd2b8821252e19a655
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788896"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="2f9c6-102">-除外 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f9c6-102">-out (Visual Basic)</span></span>
<span data-ttu-id="2f9c6-103">出力ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f9c6-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f9c6-104">構文</span><span class="sxs-lookup"><span data-stu-id="2f9c6-104">Syntax</span></span>  
  
```  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="2f9c6-105">引数</span><span class="sxs-lookup"><span data-stu-id="2f9c6-105">Arguments</span></span>  
  
|<span data-ttu-id="2f9c6-106">用語</span><span class="sxs-lookup"><span data-stu-id="2f9c6-106">Term</span></span>|<span data-ttu-id="2f9c6-107">定義</span><span class="sxs-lookup"><span data-stu-id="2f9c6-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="2f9c6-108">必須。</span><span class="sxs-lookup"><span data-stu-id="2f9c6-108">Required.</span></span> <span data-ttu-id="2f9c6-109">コンパイラの出力ファイルの名前を作成します。</span><span class="sxs-lookup"><span data-stu-id="2f9c6-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="2f9c6-110">ファイル名にスペースが含まれている場合は、名前を引用符で囲みます ("")。</span><span class="sxs-lookup"><span data-stu-id="2f9c6-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f9c6-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="2f9c6-111">Remarks</span></span>  
 <span data-ttu-id="2f9c6-112">作成するファイルの拡張機能と完全な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f9c6-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="2f9c6-113">.Exe ファイルを含むソース コード ファイルから、その名前は、そうでない場合、`Sub Main`プロシージャ、および .dll ファイルは、最初のソース コード ファイルからの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="2f9c6-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="2f9c6-114">.Exe または .dll 拡張子のないファイル名を指定するコンパイラが自動的に追加、拡張機能、指定された値に応じて、`-target`コンパイラ オプション。</span><span class="sxs-lookup"><span data-stu-id="2f9c6-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="2f9c6-115">設定 - アウト、Visual Studio 統合開発環境にする</span><span class="sxs-lookup"><span data-stu-id="2f9c6-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="2f9c6-116">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="2f9c6-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2f9c6-117">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f9c6-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="2f9c6-118">2.**[アプリケーション]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f9c6-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="2f9c6-119">3.値を変更、**アセンブリ名**ボックス。</span><span class="sxs-lookup"><span data-stu-id="2f9c6-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2f9c6-120">例</span><span class="sxs-lookup"><span data-stu-id="2f9c6-120">Example</span></span>  
 <span data-ttu-id="2f9c6-121">次のコードのコンパイル`T2.vb`出力ファイルを作成します`T2.exe`します。</span><span class="sxs-lookup"><span data-stu-id="2f9c6-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f9c6-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f9c6-122">See also</span></span>

- [<span data-ttu-id="2f9c6-123">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="2f9c6-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2f9c6-124">-ターゲット (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f9c6-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="2f9c6-125">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="2f9c6-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
