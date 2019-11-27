---
title: -imports
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 380e71e462f736d4564a37b83567007fa9461b05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332967"
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="5f77f-102">-imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f77f-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="5f77f-103">指定したアセンブリから名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="5f77f-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f77f-104">構文</span><span class="sxs-lookup"><span data-stu-id="5f77f-104">Syntax</span></span>  
  
```console  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="5f77f-105">引数</span><span class="sxs-lookup"><span data-stu-id="5f77f-105">Arguments</span></span>  
  
|<span data-ttu-id="5f77f-106">用語</span><span class="sxs-lookup"><span data-stu-id="5f77f-106">Term</span></span>|<span data-ttu-id="5f77f-107">Definition</span><span class="sxs-lookup"><span data-stu-id="5f77f-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="5f77f-108">必須。</span><span class="sxs-lookup"><span data-stu-id="5f77f-108">Required.</span></span> <span data-ttu-id="5f77f-109">インポートする名前空間のコンマ区切りの一覧。</span><span class="sxs-lookup"><span data-stu-id="5f77f-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f77f-110">コメント</span><span class="sxs-lookup"><span data-stu-id="5f77f-110">Remarks</span></span>  
 <span data-ttu-id="5f77f-111">`-imports` オプションは、ソースファイルの現在のセットまたは参照されているアセンブリの中で定義されているすべての名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="5f77f-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="5f77f-112">`-imports` で指定された名前空間のメンバーは、コンパイル時にすべてのソースコードファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f77f-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="5f77f-113">[Imports ステートメント (.Net 名前空間と型)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)を使用して、1つのソースコードファイルで名前空間を使用します。</span><span class="sxs-lookup"><span data-stu-id="5f77f-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="5f77f-114">Visual Studio 統合開発環境で/imports を設定するには</span><span class="sxs-lookup"><span data-stu-id="5f77f-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="5f77f-115">1.**ソリューションエクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="5f77f-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="5f77f-116">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f77f-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="5f77f-117">2. **[参照]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f77f-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="5f77f-118">3. **[ユーザーインポートの追加]** ボタンの横にあるボックスに名前空間名を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f77f-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="5f77f-119">4. **[ユーザーインポートの追加]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f77f-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5f77f-120">例</span><span class="sxs-lookup"><span data-stu-id="5f77f-120">Example</span></span>  
 <span data-ttu-id="5f77f-121">`/imports:system.globalization` を指定すると、次のコードがコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="5f77f-121">The following code compiles when `/imports:system.globalization` is specified.</span></span> <span data-ttu-id="5f77f-122">それがない場合、コンパイルが成功するには、ソースコードファイルの先頭に `Imports System.Globalization` ステートメントが含まれているか、プロパティが `System.Globalization.CultureInfo.CurrentCulture.Name`として完全に修飾されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f77f-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span>

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="5f77f-123">参照</span><span class="sxs-lookup"><span data-stu-id="5f77f-123">See also</span></span>

- [<span data-ttu-id="5f77f-124">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="5f77f-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5f77f-125">参照と Imports ステートメント</span><span class="sxs-lookup"><span data-stu-id="5f77f-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="5f77f-126">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="5f77f-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
