---
title: Auto
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: 799a7320b701384dc5f4b4b46fef8544f6b15b02
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875517"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="66ea0-102">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66ea0-102">Auto (Visual Basic)</span></span>

<span data-ttu-id="66ea0-103">Visual Basic で、宣言されている外部プロシージャの外部名に基づいて、.NET Framework ルールに従い、文字列をマーシャリングする必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="66ea0-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="66ea0-104">プロジェクトの外部で定義されたプロシージャを呼び出すと、Visual Basic コンパイラが、プロシージャを正しく呼び出すために必要な情報にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="66ea0-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="66ea0-105">この情報には、プロシージャの配置場所、識別方法、呼び出し元のシーケンスと戻り値の型、および使用されている文字列の文字セットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="66ea0-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="66ea0-106">[Declare ステートメント](../statements/declare-statement.md)は、外部プロシージャへの参照を作成し、この必要な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="66ea0-106">The [Declare Statement](../statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="66ea0-107">`Declare` ステートメントの `charsetmodifier` 部分では、外部プロシージャの呼び出し時に、文字列をマーシャリングするための文字セット情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="66ea0-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="66ea0-108">これは、Visual Basic が外部ファイルで外部プロシージャ名を検索する方法にも影響します。</span><span class="sxs-lookup"><span data-stu-id="66ea0-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="66ea0-109">`Auto` 修飾子は、Visual Basic が .NET Framework の規則に従って文字列をマーシャリングし、実行時プラットフォームの基本文字セットを決定して、最初の検索が失敗した場合には外部プロシージャ名を変更する可能性があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="66ea0-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="66ea0-110">詳細については、「[Declare ステートメント](../statements/declare-statement.md)」の「文字セット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66ea0-110">For more information, see "Character Sets" in [Declare Statement](../statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="66ea0-111">文字セット修飾子が指定されていない場合は、`Ansi` が既定値になります。</span><span class="sxs-lookup"><span data-stu-id="66ea0-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66ea0-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="66ea0-112">Remarks</span></span>  

 <span data-ttu-id="66ea0-113">`Auto` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="66ea0-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="66ea0-114">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="66ea0-114">Declare Statement</span></span>](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="66ea0-115">スマート デバイス開発者向けのメモ</span><span class="sxs-lookup"><span data-stu-id="66ea0-115">Smart Device Developer Notes</span></span>  

 <span data-ttu-id="66ea0-116">このキーワードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="66ea0-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66ea0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="66ea0-117">See also</span></span>

- [<span data-ttu-id="66ea0-118">Ansi</span><span class="sxs-lookup"><span data-stu-id="66ea0-118">Ansi</span></span>](ansi.md)
- [<span data-ttu-id="66ea0-119">Unicode</span><span class="sxs-lookup"><span data-stu-id="66ea0-119">Unicode</span></span>](unicode.md)
- [<span data-ttu-id="66ea0-120">キーワード</span><span class="sxs-lookup"><span data-stu-id="66ea0-120">Keywords</span></span>](../keywords/index.md)
