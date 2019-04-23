---
title: 序数が有効ではありません。
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 28f78161e14604c1f59872801855ccc918faec58
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59299255"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="8dd21-102">序数が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="8dd21-102">Ordinal is not valid</span></span>
<span data-ttu-id="8dd21-103">プロシージャ名ではなく番号を使用するダイナミック リンク ライブラリ (DLL) への呼び出しが示されるを使用して、`#num`構文。</span><span class="sxs-lookup"><span data-stu-id="8dd21-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="8dd21-104">このエラーは、次の考えられる原因があります。</span><span class="sxs-lookup"><span data-stu-id="8dd21-104">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="8dd21-105">変換、`#num`序数が失敗する式。</span><span class="sxs-lookup"><span data-stu-id="8dd21-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
-   <span data-ttu-id="8dd21-106">`#num`指定された DLL で任意の関数を指定できません。</span><span class="sxs-lookup"><span data-stu-id="8dd21-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
-   <span data-ttu-id="8dd21-107">タイプ ライブラリには、無効な序数の内部使用の無効な宣言があります。</span><span class="sxs-lookup"><span data-stu-id="8dd21-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8dd21-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="8dd21-108">To correct this error</span></span>  
  
1. <span data-ttu-id="8dd21-109">名前でプロシージャを呼び出す、または式が有効な数値を表すかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8dd21-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2. <span data-ttu-id="8dd21-110">必ず`#num`DLL 内の有効な関数を識別します。</span><span class="sxs-lookup"><span data-stu-id="8dd21-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3. <span data-ttu-id="8dd21-111">問題の原因で、コードのコメント アウト、プロシージャの呼び出しを分離します。</span><span class="sxs-lookup"><span data-stu-id="8dd21-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="8dd21-112">書き込みを`Declare`プロシージャと、タイプ ライブラリのベンダーの問題の報告ステートメント。</span><span class="sxs-lookup"><span data-stu-id="8dd21-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dd21-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="8dd21-113">See also</span></span>

- [<span data-ttu-id="8dd21-114">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="8dd21-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
