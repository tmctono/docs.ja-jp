---
title: .NET Framework 型の文字列への変換
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
ms.openlocfilehash: a63e0175f6660967eb4aa678c6731d353e44e2d5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711078"
---
# <a name="converting-net-framework-types-to-strings"></a><span data-ttu-id="62923-102">.NET Framework 型の文字列への変換</span><span class="sxs-lookup"><span data-stu-id="62923-102">Converting .NET Framework Types to Strings</span></span>
<span data-ttu-id="62923-103">.NET Framework 型を文字列に変換するには、**ToString** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="62923-103">If you want to convert a .NET Framework type to a string, use the **ToString** method.</span></span> <span data-ttu-id="62923-104">**ToString** メソッドは、渡された型の文字列表現を返します。</span><span class="sxs-lookup"><span data-stu-id="62923-104">The **ToString** method returns a string representation of the type passed in.</span></span> <span data-ttu-id="62923-105">XML スキーマ (XSD) 仕様に対応する形式で文字列を返す .NET Framework 型を、次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="62923-105">The following table lists the .NET Framework types that return a string in a format that maps to the XML Schema (XSD) specifications.</span></span>  
  
|<span data-ttu-id="62923-106">.NET Framework 型</span><span class="sxs-lookup"><span data-stu-id="62923-106">.NET Framework type</span></span>|<span data-ttu-id="62923-107">返される文字列型</span><span class="sxs-lookup"><span data-stu-id="62923-107">String type returned</span></span>|  
|-------------------------|--------------------------|  
|<span data-ttu-id="62923-108">Boolean</span><span class="sxs-lookup"><span data-stu-id="62923-108">Boolean</span></span>|<span data-ttu-id="62923-109">"true"、"false"</span><span class="sxs-lookup"><span data-stu-id="62923-109">"true", "false"</span></span>|  
|<span data-ttu-id="62923-110">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="62923-110">Single.PositiveInfinity</span></span>|<span data-ttu-id="62923-111">"INF"</span><span class="sxs-lookup"><span data-stu-id="62923-111">"INF"</span></span>|  
|<span data-ttu-id="62923-112">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="62923-112">Single.NegativeInfinity</span></span>|<span data-ttu-id="62923-113">"-INF"</span><span class="sxs-lookup"><span data-stu-id="62923-113">"-INF"</span></span>|  
|<span data-ttu-id="62923-114">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="62923-114">Double.PositiveInfinity</span></span>|<span data-ttu-id="62923-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="62923-115">"INF"</span></span>|  
|<span data-ttu-id="62923-116">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="62923-116">Double.NegativeInfinity</span></span>|<span data-ttu-id="62923-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="62923-117">"-INF"</span></span>|  
|<span data-ttu-id="62923-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="62923-118">DateTime</span></span>|<span data-ttu-id="62923-119">形式は、yyyy-MM-ddTHH:mm:sszzzzzz およびそのサブセットです。</span><span class="sxs-lookup"><span data-stu-id="62923-119">Format is yyyy-MM-ddTHH:mm:sszzzzzz and its subsets.</span></span>|  
|<span data-ttu-id="62923-120">Timespan</span><span class="sxs-lookup"><span data-stu-id="62923-120">Timespan</span></span>|<span data-ttu-id="62923-121">PnYnMnTnHnMnS の形式。たとえば、`P2Y10M15DT10H30M20S` は 2 年 10 か月 15 日 10 時間 30 分 20 秒の期間です。</span><span class="sxs-lookup"><span data-stu-id="62923-121">Format is PnYnMnTnHnMnS, for example, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10hours, 30 minutes and 20 seconds.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62923-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="62923-122">See also</span></span>

- [<span data-ttu-id="62923-123">XML データ型の変換</span><span class="sxs-lookup"><span data-stu-id="62923-123">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)
- [<span data-ttu-id="62923-124">文字列の .NET Framework データ型への変換</span><span class="sxs-lookup"><span data-stu-id="62923-124">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
