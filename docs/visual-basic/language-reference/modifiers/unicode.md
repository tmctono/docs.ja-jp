---
title: Unicode
ms.date: 07/20/2015
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
ms.openlocfilehash: c4286ed9e9d5fd768ae29b7050b3d1505ccca9dd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344220"
---
# <a name="unicode-visual-basic"></a><span data-ttu-id="8d169-102">Unicode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d169-102">Unicode (Visual Basic)</span></span>
<span data-ttu-id="8d169-103">宣言する外部プロシージャの名前に関係なく、すべての文字列を Unicode 値にマーシャリング Visual Basic 必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="8d169-103">Specifies that Visual Basic should marshal all strings to Unicode values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="8d169-104">プロジェクトの外部で定義されたプロシージャを呼び出すと、Visual Basic コンパイラは、プロシージャを正しく呼び出すために必要な情報にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="8d169-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have in order to call the procedure correctly.</span></span> <span data-ttu-id="8d169-105">この情報には、プロシージャの配置場所、識別方法、呼び出し元のシーケンスと戻り値の型、および使用する文字列文字セットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8d169-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="8d169-106">[Declare ステートメント](../../../visual-basic/language-reference/statements/declare-statement.md)は、外部プロシージャへの参照を作成し、この必要な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="8d169-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="8d169-107">`Declare` ステートメントの `charsetmodifier` 部分では、外部プロシージャの呼び出し時に文字列をマーシャリングするための文字セット情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d169-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information to marshal strings during a call to the external procedure.</span></span> <span data-ttu-id="8d169-108">また、外部ファイルで外部プロシージャ名を検索 Visual Basic 方法にも影響します。</span><span class="sxs-lookup"><span data-stu-id="8d169-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="8d169-109">`Unicode` 修飾子は、Visual Basic がすべての文字列を Unicode 値にマーシャリングする必要があることを指定します。また、検索時には、プロシージャの名前を変更せずにプロシージャを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d169-109">The `Unicode` modifier specifies that Visual Basic should marshal all strings to Unicode values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="8d169-110">文字セット修飾子が指定されていない場合は、`Ansi` が既定値になります。</span><span class="sxs-lookup"><span data-stu-id="8d169-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d169-111">コメント</span><span class="sxs-lookup"><span data-stu-id="8d169-111">Remarks</span></span>  
 <span data-ttu-id="8d169-112">このコンテキストでは、`Unicode` 修飾子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d169-112">The `Unicode` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="8d169-113">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="8d169-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="8d169-114">スマートデバイスの開発者向けメモ</span><span class="sxs-lookup"><span data-stu-id="8d169-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="8d169-115">このキーワードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8d169-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d169-116">参照</span><span class="sxs-lookup"><span data-stu-id="8d169-116">See also</span></span>

- [<span data-ttu-id="8d169-117">Ansi</span><span class="sxs-lookup"><span data-stu-id="8d169-117">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)
- [<span data-ttu-id="8d169-118">Auto</span><span class="sxs-lookup"><span data-stu-id="8d169-118">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)
- [<span data-ttu-id="8d169-119">キーワード</span><span class="sxs-lookup"><span data-stu-id="8d169-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
