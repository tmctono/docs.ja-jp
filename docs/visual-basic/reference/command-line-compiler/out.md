---
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 67366e13e4dceea4772d0730222413cb25b4e8b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352390"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="ac44d-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac44d-102">-out (Visual Basic)</span></span>
<span data-ttu-id="ac44d-103">出力ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac44d-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac44d-104">構文</span><span class="sxs-lookup"><span data-stu-id="ac44d-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="ac44d-105">引数</span><span class="sxs-lookup"><span data-stu-id="ac44d-105">Arguments</span></span>  
  
|<span data-ttu-id="ac44d-106">用語</span><span class="sxs-lookup"><span data-stu-id="ac44d-106">Term</span></span>|<span data-ttu-id="ac44d-107">Definition</span><span class="sxs-lookup"><span data-stu-id="ac44d-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="ac44d-108">必須。</span><span class="sxs-lookup"><span data-stu-id="ac44d-108">Required.</span></span> <span data-ttu-id="ac44d-109">コンパイラによって作成される出力ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="ac44d-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="ac44d-110">ファイル名にスペースが含まれている場合は、名前を引用符 ("") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="ac44d-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac44d-111">コメント</span><span class="sxs-lookup"><span data-stu-id="ac44d-111">Remarks</span></span>  
 <span data-ttu-id="ac44d-112">作成するファイルの完全な名前と拡張子を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac44d-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="ac44d-113">そうしないと、.exe ファイルの名前が `Sub Main` プロシージャを含むソースコードファイルから取得され、.dll ファイルの名前が最初のソースコードファイルの名前になります。</span><span class="sxs-lookup"><span data-stu-id="ac44d-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="ac44d-114">.Exe または .dll 拡張子のないファイル名を指定すると、コンパイラは、`-target` コンパイラオプションに指定された値に応じて、自動的に拡張機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="ac44d-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="ac44d-115">Visual Studio 統合開発環境でを設定するには</span><span class="sxs-lookup"><span data-stu-id="ac44d-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="ac44d-116">1.**ソリューションエクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac44d-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ac44d-117">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac44d-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="ac44d-118">2. **[アプリケーション]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac44d-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="ac44d-119">3. **[アセンブリ名]** ボックスの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="ac44d-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ac44d-120">例</span><span class="sxs-lookup"><span data-stu-id="ac44d-120">Example</span></span>  
 <span data-ttu-id="ac44d-121">次のコードは `T2.vb` をコンパイルし、出力ファイル `T2.exe`を作成します。</span><span class="sxs-lookup"><span data-stu-id="ac44d-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac44d-122">参照</span><span class="sxs-lookup"><span data-stu-id="ac44d-122">See also</span></span>

- [<span data-ttu-id="ac44d-123">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="ac44d-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ac44d-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac44d-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="ac44d-125">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="ac44d-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
