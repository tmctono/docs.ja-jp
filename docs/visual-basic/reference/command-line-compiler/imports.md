---
title: -imports
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 69781dff1474e42ae5f735fdefd694c6447636b5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085257"
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="668c4-102">-imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="668c4-102">-imports (Visual Basic)</span></span>

<span data-ttu-id="668c4-103">指定されたアセンブリから名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="668c4-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="668c4-104">構文</span><span class="sxs-lookup"><span data-stu-id="668c4-104">Syntax</span></span>  
  
```console  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="668c4-105">引数</span><span class="sxs-lookup"><span data-stu-id="668c4-105">Arguments</span></span>  
  
|<span data-ttu-id="668c4-106">用語</span><span class="sxs-lookup"><span data-stu-id="668c4-106">Term</span></span>|<span data-ttu-id="668c4-107">定義</span><span class="sxs-lookup"><span data-stu-id="668c4-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="668c4-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="668c4-108">Required.</span></span> <span data-ttu-id="668c4-109">インポートされる名前空間のコンマ区切りの一覧。</span><span class="sxs-lookup"><span data-stu-id="668c4-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="668c4-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="668c4-110">Remarks</span></span>  

 <span data-ttu-id="668c4-111">`-imports` オプションでは、参照アセンブリから、あるいはソース ファイルの現在のセット内に定義されている名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="668c4-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="668c4-112">`-imports` で指定された名前空間のメンバーは、コンパイル時にすべてのソースコード ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="668c4-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="668c4-113">単一のソースコード ファイルで名前空間を使用するには、[ ステートメント (.NET 名前空間および型)](../../language-reference/statements/imports-statement-net-namespace-and-type.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="668c4-113">Use the [Imports Statement (.NET Namespace and Type)](../../language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="668c4-114">Visual Studio 統合開発環境で -imports を設定するには</span><span class="sxs-lookup"><span data-stu-id="668c4-114">To set -imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="668c4-115">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="668c4-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="668c4-116">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="668c4-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="668c4-117">2. **[参照]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="668c4-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="668c4-118">3. **[ユーザー インポートの追加]** ボタンの横にあるボックスに、名前空間の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="668c4-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="668c4-119">4. **[ユーザー インポートの追加]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="668c4-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="668c4-120">例</span><span class="sxs-lookup"><span data-stu-id="668c4-120">Example</span></span>  

 <span data-ttu-id="668c4-121">`-imports:system.globalization` が指定されている場合、次のコードがコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="668c4-121">The following code compiles when `-imports:system.globalization` is specified.</span></span> <span data-ttu-id="668c4-122">それがない場合、正常にコンパイルするには、ソース コード ファイルの先頭に `Imports System.Globalization` ステートメントを含めるか、プロパティを `System.Globalization.CultureInfo.CurrentCulture.Name` として完全に修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="668c4-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span>

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="668c4-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="668c4-123">See also</span></span>

- [<span data-ttu-id="668c4-124">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="668c4-124">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="668c4-125">参照と Imports ステートメント</span><span class="sxs-lookup"><span data-stu-id="668c4-125">References and the Imports Statement</span></span>](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="668c4-126">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="668c4-126">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
