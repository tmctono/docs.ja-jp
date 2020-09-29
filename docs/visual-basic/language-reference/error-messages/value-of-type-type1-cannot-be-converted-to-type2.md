---
title: 型 'type1' の値を 'type2' に変換できません
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 8c80429db618e1bcadce1a58a6514d625f0b3cf1
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870229"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a><span data-ttu-id="208c1-102">型 'type1' の値を 'type2' に変換できません</span><span class="sxs-lookup"><span data-stu-id="208c1-102">Value of type 'type1' cannot be converted to 'type2'</span></span>

<span data-ttu-id="208c1-103">型 'type1' の値を 'type2' に変換できません。</span><span class="sxs-lookup"><span data-stu-id="208c1-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="208c1-104">'\<parentElement>' の最初の要素の文字列値は、'Value' プロパティを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="208c1-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="208c1-105">XML リテラルを特定の型を暗黙的にキャストしようとしました。</span><span class="sxs-lookup"><span data-stu-id="208c1-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="208c1-106">XML リテラルは、指定した型に暗黙的にキャストできません。</span><span class="sxs-lookup"><span data-stu-id="208c1-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="208c1-107">**エラー ID:** BC31194</span><span class="sxs-lookup"><span data-stu-id="208c1-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="208c1-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="208c1-108">To correct this error</span></span>  
  
- <span data-ttu-id="208c1-109">XML リテラルの `Value` プロパティを使用して、その値を `String`として参照します。</span><span class="sxs-lookup"><span data-stu-id="208c1-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="208c1-110">`CType` 関数、別の型変換関数、または <xref:System.Convert> クラスを使用して、指定した型として値をキャストします。</span><span class="sxs-lookup"><span data-stu-id="208c1-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="208c1-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="208c1-111">See also</span></span>

- <xref:System.Convert>
- [<span data-ttu-id="208c1-112">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="208c1-112">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="208c1-113">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="208c1-113">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="208c1-114">XML</span><span class="sxs-lookup"><span data-stu-id="208c1-114">XML</span></span>](../../programming-guide/language-features/xml/index.md)
