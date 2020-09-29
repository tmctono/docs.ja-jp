---
title: Narrowing
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: 77515357ac9dc972992df09c471695aad13985c4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867931"
---
# <a name="narrowing-visual-basic"></a><span data-ttu-id="3eebd-102">Narrowing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3eebd-102">Narrowing (Visual Basic)</span></span>

<span data-ttu-id="3eebd-103">変換演算子 (`CType`) で、クラスまたは構造体を、元のクラスまたは構造体の一部の使用可能な値を保持できない可能性がある型に変換することを示します。</span><span class="sxs-lookup"><span data-stu-id="3eebd-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that might not be able to hold some of the possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-narrowing-keyword"></a><span data-ttu-id="3eebd-104">Narrowing キーワードを使用した変換</span><span class="sxs-lookup"><span data-stu-id="3eebd-104">Converting with the Narrowing Keyword</span></span>  

 <span data-ttu-id="3eebd-105">変換プロシージャでは、`Narrowing` に加えて `Public Shared` を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3eebd-105">The conversion procedure must specify `Public Shared` in addition to `Narrowing`.</span></span>  
  
 <span data-ttu-id="3eebd-106">縮小変換は実行時に必ず成功するとは限らず、失敗したり、データの損失が発生したりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3eebd-106">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="3eebd-107">例として、`Long` から `Integer`、`String` から `Date`、および基本型から派生型があります。</span><span class="sxs-lookup"><span data-stu-id="3eebd-107">Examples are `Long` to `Integer`, `String` to `Date`, and a base type to a derived type.</span></span> <span data-ttu-id="3eebd-108">基本型には派生型のすべてのメンバーが含まれていない場合があり、派生型のインスタンスではないため、この最後の変換は縮小変換になります。</span><span class="sxs-lookup"><span data-stu-id="3eebd-108">This last conversion is narrowing because the base type might not contain all the members of the derived type and thus is not an instance of the derived type.</span></span>  
  
 <span data-ttu-id="3eebd-109">`Option Strict` が `On` の場合、使用しているコードではすべての縮小変換に `CType` を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3eebd-109">If `Option Strict` is `On`, the consuming code must use `CType` for all narrowing conversions.</span></span>  
  
 <span data-ttu-id="3eebd-110">`Narrowing` キーワードは次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="3eebd-110">The `Narrowing` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="3eebd-111">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="3eebd-111">Operator Statement</span></span>](../statements/operator-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="3eebd-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="3eebd-112">See also</span></span>

- [<span data-ttu-id="3eebd-113">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="3eebd-113">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="3eebd-114">Widening</span><span class="sxs-lookup"><span data-stu-id="3eebd-114">Widening</span></span>](widening.md)
- [<span data-ttu-id="3eebd-115">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="3eebd-115">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="3eebd-116">方法: 演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="3eebd-116">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="3eebd-117">CType 関数</span><span class="sxs-lookup"><span data-stu-id="3eebd-117">CType Function</span></span>](../functions/ctype-function.md)
- [<span data-ttu-id="3eebd-118">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="3eebd-118">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
