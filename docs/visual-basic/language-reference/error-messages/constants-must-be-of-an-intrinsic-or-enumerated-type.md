---
title: 定数は、class、structure、または array 型ではなく、組み込み型または列挙型でなければなりません。
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: 88bbab2005b464ee97d647f2b4b9be6ff81e2d82
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61649843"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a><span data-ttu-id="91a07-102">定数は、class、structure、または array 型ではなく、組み込み型または列挙型でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="91a07-102">Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type</span></span>
<span data-ttu-id="91a07-103">クラス、構造体、または配列型、またはそれを含むジェネリック型で定義された型パラメーターと定数を宣言しようとしました。</span><span class="sxs-lookup"><span data-stu-id="91a07-103">You have attempted to declare a constant as a class, structure, or array type, or as a type parameter defined by a containing generic type.</span></span>  
  
 <span data-ttu-id="91a07-104">組み込み型の定数があります (`Boolean`、 `Byte`、 `Date`、 `Decimal`、 `Double`、 `Integer`、 `Long`、 `Object`、 `SByte`、 `Short`、 `Single`、 `String`、 `UInteger`、 `ULong`、または`UShort`)、または`Enum`型が整数型のいずれかに基づきます。</span><span class="sxs-lookup"><span data-stu-id="91a07-104">Constants must be of an intrinsic type (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, or `UShort`), or an `Enum` type based on one of the integral types.</span></span>  
  
 <span data-ttu-id="91a07-105">**エラー ID:** BC30424</span><span class="sxs-lookup"><span data-stu-id="91a07-105">**Error ID:** BC30424</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="91a07-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="91a07-106">To correct this error</span></span>  
  
1. <span data-ttu-id="91a07-107">組み込み関数として定数を宣言または`Enum`型。</span><span class="sxs-lookup"><span data-stu-id="91a07-107">Declare the constant as an intrinsic or `Enum` type.</span></span>  
  
2. <span data-ttu-id="91a07-108">定数にはまた、特殊な値など`True`、 `False`、または`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="91a07-108">A constant can also be a special value such as `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="91a07-109">コンパイラでは、これらの定義済み値の適切な組み込み型と見なします。</span><span class="sxs-lookup"><span data-stu-id="91a07-109">The compiler considers these predefined values to be of the appropriate intrinsic type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a07-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="91a07-110">See also</span></span>

- [<span data-ttu-id="91a07-111">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="91a07-111">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="91a07-112">データの種類</span><span class="sxs-lookup"><span data-stu-id="91a07-112">Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="91a07-113">データの種類</span><span class="sxs-lookup"><span data-stu-id="91a07-113">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
