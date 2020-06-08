---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: 5530da4c784346df4a1088998b8d2027feee08e3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403162"
---
# <a name="-main"></a><span data-ttu-id="b43be-102">-main</span><span class="sxs-lookup"><span data-stu-id="b43be-102">-main</span></span>
<span data-ttu-id="b43be-103">`Sub Main` プロシージャを格納するクラスまたはモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="b43be-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b43be-104">構文</span><span class="sxs-lookup"><span data-stu-id="b43be-104">Syntax</span></span>  
  
```console  
-main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="b43be-105">引数</span><span class="sxs-lookup"><span data-stu-id="b43be-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="b43be-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="b43be-106">Required.</span></span> <span data-ttu-id="b43be-107">プログラムの起動時に呼び出される `Sub Main` プロシージャを含むクラスまたはモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="b43be-107">The name of the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="b43be-108">この形式は、 **-main:module** または **-main:namespace.module** である場合があります。</span><span class="sxs-lookup"><span data-stu-id="b43be-108">This may be in the form **-main:module** or **-main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b43be-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="b43be-109">Remarks</span></span>  
 <span data-ttu-id="b43be-110">このオプションは、実行可能ファイルまたは Windows 実行可能プログラムを作成するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="b43be-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="b43be-111">**-main** オプションを省略した場合、すべてのパブリック クラスとモジュールから、有効な共有 `Sub Main` がコンパイラにより検索されます。</span><span class="sxs-lookup"><span data-stu-id="b43be-111">If the **-main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="b43be-112">`Main` プロシージャのさまざまな形式については、「[Visual Basic の Main プロシージャ](../../programming-guide/program-structure/main-procedure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b43be-112">See [Main Procedure in Visual Basic](../../programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="b43be-113">`location` が <xref:System.Windows.Forms.Form> から継承されるクラスである場合にクラスに `Main` プロシージャがないとき、アプリケーションを起動する既定の `Main` プロシージャがコンパイラによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="b43be-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="b43be-114">これにより、開発環境で作成されたコードを、コマンド ラインでコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="b43be-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="b43be-115">Visual Studio 統合開発環境で -main を設定するには</span><span class="sxs-lookup"><span data-stu-id="b43be-115">To set -main in the Visual Studio integrated development environment</span></span>  
  
1. <span data-ttu-id="b43be-116">**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="b43be-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="b43be-117">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b43be-117">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="b43be-118">**[アプリケーション]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b43be-118">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="b43be-119">**[アプリケーション フレームワークを有効にする]** チェック ボックスがオフになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b43be-119">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4. <span data-ttu-id="b43be-120">**[スタートアップ オブジェクト]** ボックスの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="b43be-120">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b43be-121">例</span><span class="sxs-lookup"><span data-stu-id="b43be-121">Example</span></span>  
 <span data-ttu-id="b43be-122">次のコードでは、`Sub Main` プロシージャが `Test2` クラスにあることが指定され、`T2.vb` と `T3.vb` がコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="b43be-122">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="b43be-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="b43be-123">See also</span></span>

- [<span data-ttu-id="b43be-124">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="b43be-124">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="b43be-125">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b43be-125">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="b43be-126">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="b43be-126">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="b43be-127">Visual Basic の Main プロシージャ</span><span class="sxs-lookup"><span data-stu-id="b43be-127">Main Procedure in Visual Basic</span></span>](../../programming-guide/program-structure/main-procedure.md)
