---
title: Ansi
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: 0c38c2b81af7b4cb8fd1723853a09c5413f805af
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344737"
---
# <a name="ansi-visual-basic"></a><span data-ttu-id="fd9a8-102">Ansi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd9a8-102">Ansi (Visual Basic)</span></span>
<span data-ttu-id="fd9a8-103">宣言する外部プロシージャの名前に関係なく、すべての文字列を米国規格協会 (ANSI) (ANSI) 値にマーシャリング Visual Basic 必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="fd9a8-103">Specifies that Visual Basic should marshal all strings to American National Standards Institute (ANSI) values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="fd9a8-104">プロジェクトの外部で定義されたプロシージャを呼び出すと、Visual Basic コンパイラは、プロシージャを正しく呼び出すために必要な情報にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="fd9a8-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it needs to call the procedure correctly.</span></span> <span data-ttu-id="fd9a8-105">この情報には、プロシージャの配置場所、識別方法、呼び出し元のシーケンスと戻り値の型、および使用する文字列文字セットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fd9a8-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="fd9a8-106">[Declare ステートメント](../../../visual-basic/language-reference/statements/declare-statement.md)は、外部プロシージャへの参照を作成し、この必要な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="fd9a8-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="fd9a8-107">`Declare` ステートメントの `charsetmodifier` 部分では、外部プロシージャの呼び出し時に文字列をマーシャリングするための文字セット情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="fd9a8-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="fd9a8-108">また、外部ファイルで外部プロシージャ名を検索 Visual Basic 方法にも影響します。</span><span class="sxs-lookup"><span data-stu-id="fd9a8-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="fd9a8-109">`Ansi` 修飾子は、Visual Basic がすべての文字列を ANSI 値にマーシャリングする必要があることを指定します。検索中は、プロシージャの名前を変更せずにプロシージャを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd9a8-109">The `Ansi` modifier specifies that Visual Basic should marshal all strings to ANSI values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="fd9a8-110">文字セット修飾子が指定されていない場合は、`Ansi` が既定値になります。</span><span class="sxs-lookup"><span data-stu-id="fd9a8-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd9a8-111">コメント</span><span class="sxs-lookup"><span data-stu-id="fd9a8-111">Remarks</span></span>  
 <span data-ttu-id="fd9a8-112">このコンテキストでは、`Ansi` 修飾子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fd9a8-112">The `Ansi` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="fd9a8-113">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="fd9a8-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="fd9a8-114">スマートデバイスの開発者向けメモ</span><span class="sxs-lookup"><span data-stu-id="fd9a8-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="fd9a8-115">このキーワードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fd9a8-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd9a8-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd9a8-116">See also</span></span>

- [<span data-ttu-id="fd9a8-117">Auto</span><span class="sxs-lookup"><span data-stu-id="fd9a8-117">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)
- [<span data-ttu-id="fd9a8-118">Unicode</span><span class="sxs-lookup"><span data-stu-id="fd9a8-118">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)
- [<span data-ttu-id="fd9a8-119">キーワード</span><span class="sxs-lookup"><span data-stu-id="fd9a8-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
