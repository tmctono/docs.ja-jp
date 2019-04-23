---
title: Sub または Function が定義されていません。(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 397648618ea3764efafb5cff41deaef320bbeff3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59294679"
---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="5fd47-102">Sub または Function が定義されていません。(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5fd47-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="5fd47-103">A`Sub`または`Function`呼び出すには定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fd47-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="5fd47-104">このエラーでは以下の原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="5fd47-104">Possible causes of this error include:</span></span>  
  
-   <span data-ttu-id="5fd47-105">プロシージャ名のスペルが間違っています。</span><span class="sxs-lookup"><span data-stu-id="5fd47-105">Misspelling the procedure name.</span></span>  
  
-   <span data-ttu-id="5fd47-106">別のプロジェクトからでは、そのプロジェクトへの参照を明示的に追加せず、プロシージャを呼び出そうとしている、**参照** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="5fd47-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
-   <span data-ttu-id="5fd47-107">呼び出し元のプロシージャには表示されないプロシージャを指定します。</span><span class="sxs-lookup"><span data-stu-id="5fd47-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
-   <span data-ttu-id="5fd47-108">Windows ダイナミック リンク ライブラリ (DLL) のルーチンまたは指定したライブラリまたはコード リソース内にない Macintosh コード リソースのルーチンを宣言します。</span><span class="sxs-lookup"><span data-stu-id="5fd47-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5fd47-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="5fd47-109">To correct this error</span></span>  
  
1. <span data-ttu-id="5fd47-110">プロシージャ名のスペルが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fd47-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2. <span data-ttu-id="5fd47-111">呼び出そうとプロシージャを含むプロジェクトの名前を検索、**参照** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="5fd47-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="5fd47-112">表示されない場合は、クリックして、**参照**検索ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd47-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="5fd47-113">プロジェクト名の左側にチェック ボックスを選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="5fd47-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="5fd47-114">ルーチンの名前を確認します。</span><span class="sxs-lookup"><span data-stu-id="5fd47-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fd47-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5fd47-115">See also</span></span>

- [<span data-ttu-id="5fd47-116">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="5fd47-116">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="5fd47-117">プロジェクト内の参照の管理</span><span class="sxs-lookup"><span data-stu-id="5fd47-117">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="5fd47-118">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="5fd47-118">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="5fd47-119">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="5fd47-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
