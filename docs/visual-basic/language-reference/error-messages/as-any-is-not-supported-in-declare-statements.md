---
title: "'As Any' は、'Declare' ステートメントではサポートされていません。"
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: 3593f238c72cbcce911c72e42552d6a75188b628
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935331"
---
# <a name="as-any-is-not-supported-in-declare-statements"></a><span data-ttu-id="4571d-102">'As Any' は、'Declare' ステートメントではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4571d-102">'As Any' is not supported in 'Declare' statements</span></span>
<span data-ttu-id="4571d-103">`Any`データ型の併用`Declare`ステートメントでは、あらゆる種類のデータを含む可能性のある引数の使用を許可するには、Visual Basic 6.0 と以前のバージョン。</span><span class="sxs-lookup"><span data-stu-id="4571d-103">The `Any` data type was used with `Declare` statements in Visual Basic 6.0 and earlier versions to permit the use of arguments that could contain any type of data.</span></span> <span data-ttu-id="4571d-104">オーバー ロード、ただし、Visual Basic は、そのにより、`Any`データ型の廃止されています。</span><span class="sxs-lookup"><span data-stu-id="4571d-104">Visual Basic supports overloading, however, and so makes the `Any` data type obsolete.</span></span>  
  
 <span data-ttu-id="4571d-105">**エラー ID:** BC30828</span><span class="sxs-lookup"><span data-stu-id="4571d-105">**Error ID:** BC30828</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4571d-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="4571d-106">To correct this error</span></span>  
  
1. <span data-ttu-id="4571d-107">を使用する特定の型のパラメーターを宣言します。例えば。</span><span class="sxs-lookup"><span data-stu-id="4571d-107">Declare parameters of the specific type you want to use; for example.</span></span>  
  
     [!code-vb[VbVbalrStatements#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#95)]  
  
2. <span data-ttu-id="4571d-108">使用して、<xref:System.Runtime.InteropServices.MarshalAsAttribute>属性を指定する`As Any`とき`Void*`によって呼び出されるプロシージャが必要です。</span><span class="sxs-lookup"><span data-stu-id="4571d-108">Use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify `As Any` when `Void*` is expected by the procedure being called.</span></span>  
  
     [!code-vb[VbVbalrStatements#96](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#96)]  
  
## <a name="see-also"></a><span data-ttu-id="4571d-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="4571d-109">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="4571d-110">チュートリアル: Windows API の呼び出し</span><span class="sxs-lookup"><span data-stu-id="4571d-110">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="4571d-111">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="4571d-111">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="4571d-112">マネージド コードでのプロトタイプの作成</span><span class="sxs-lookup"><span data-stu-id="4571d-112">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
