---
title: -インポート (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 075eeccc7d80943d2757a97b9a355bbea3ef9d4e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833610"
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="c2820-102">-インポート (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2820-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="c2820-103">指定したアセンブリから名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="c2820-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2820-104">構文</span><span class="sxs-lookup"><span data-stu-id="c2820-104">Syntax</span></span>  
  
```  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="c2820-105">引数</span><span class="sxs-lookup"><span data-stu-id="c2820-105">Arguments</span></span>  
  
|<span data-ttu-id="c2820-106">用語</span><span class="sxs-lookup"><span data-stu-id="c2820-106">Term</span></span>|<span data-ttu-id="c2820-107">定義</span><span class="sxs-lookup"><span data-stu-id="c2820-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="c2820-108">必須。</span><span class="sxs-lookup"><span data-stu-id="c2820-108">Required.</span></span> <span data-ttu-id="c2820-109">インポートする名前空間のコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="c2820-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2820-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="c2820-110">Remarks</span></span>  
 <span data-ttu-id="c2820-111">`-imports`オプションは、現在のソース ファイルまたは参照先アセンブリのセット内で定義されている任意の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="c2820-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="c2820-112">指定された名前空間内のメンバー`-imports`コンパイルですべてのソース コード ファイルを利用できます。</span><span class="sxs-lookup"><span data-stu-id="c2820-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="c2820-113">使用して、 [Imports ステートメント (.NET Namespace よぶ型)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)を 1 つのソース コード ファイルの名前空間を使用します。</span><span class="sxs-lookup"><span data-stu-id="c2820-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="c2820-114">設定する]、[Visual Studio 統合開発環境のインポート</span><span class="sxs-lookup"><span data-stu-id="c2820-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="c2820-115">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="c2820-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c2820-116">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2820-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="c2820-117">2.**[参照]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2820-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="c2820-118">3.横にあるボックスに名前空間の名前を入力、**ユーザー インポートの追加**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2820-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="c2820-119">4.をクリックして、**ユーザー インポートの追加**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2820-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c2820-120">例</span><span class="sxs-lookup"><span data-stu-id="c2820-120">Example</span></span>  
 <span data-ttu-id="c2820-121">ときに、次のコードがコンパイル`/imports:system.globalization`を指定します。</span><span class="sxs-lookup"><span data-stu-id="c2820-121">The following code compiles when `/imports:system.globalization` is specified.</span></span> <span data-ttu-id="c2820-122">それなしに正常にコンパイルする必要がありますか、`Imports System.Globalization`ステートメントは、ソース コード ファイルの先頭に必ず、またはプロパティとして完全修飾`System.Globalization.CultureInfo.CurrentCulture.Name`します。</span><span class="sxs-lookup"><span data-stu-id="c2820-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span>

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="c2820-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2820-123">See also</span></span>

- [<span data-ttu-id="c2820-124">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="c2820-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="c2820-125">参照と Imports ステートメント</span><span class="sxs-lookup"><span data-stu-id="c2820-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="c2820-126">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="c2820-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
