---
title: '方法: リフレクションを使用して型とメンバーの情報を取得する'
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
author: rpetrusha
ms.author: ronpet
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: da71845ea276267220636cfd661465ea02b2b50d
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972859"
---
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a><span data-ttu-id="9fac9-102">方法: リフレクションを使用して型とメンバーの情報を取得する</span><span class="sxs-lookup"><span data-stu-id="9fac9-102">How to: Get type and member information by using reflection</span></span>
<span data-ttu-id="9fac9-103"><xref:System.Reflection> 名前空間には、型とそのメンバーに関する情報を取得するための多くのメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="9fac9-103">The <xref:System.Reflection> namespace contains many methods for obtaining information about types and their members.</span></span> <span data-ttu-id="9fac9-104">この記事では、これらのメソッドの 1 つである <xref:System.Type.GetMembers%2A?displayProperty=nameWithType> を例として示します。</span><span class="sxs-lookup"><span data-stu-id="9fac9-104">This article demonstrates one of these methods, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9fac9-105">詳細については、「[リフレクションの概要](reflection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fac9-105">For additional information, see [Reflection overview](reflection.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="9fac9-106">例</span><span class="sxs-lookup"><span data-stu-id="9fac9-106">Example</span></span>

<span data-ttu-id="9fac9-107">リフレクションを使用して型とメンバーの情報を取得する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9fac9-107">The following example obtains type and member information by using reflection:</span></span>

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a><span data-ttu-id="9fac9-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="9fac9-108">See also</span></span>

- [<span data-ttu-id="9fac9-109">アプリケーション ドメインを使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="9fac9-109">Program with application domains</span></span>](../app-domains/application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="9fac9-110">リフレクション</span><span class="sxs-lookup"><span data-stu-id="9fac9-110">Reflection</span></span>](reflection.md)
- [<span data-ttu-id="9fac9-111">アプリケーション ドメインを使用する</span><span class="sxs-lookup"><span data-stu-id="9fac9-111">Use application domains</span></span>](../app-domains/use.md)
