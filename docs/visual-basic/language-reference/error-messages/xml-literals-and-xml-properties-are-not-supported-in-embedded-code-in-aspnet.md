---
title: XML リテラルおよび XML プロパティは、ASP.NET 内の埋め込みコードではサポートされません
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: bda92b4244631f66142499a94be562854b35437e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406470"
---
# <a name="xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a><span data-ttu-id="faef5-102">XML リテラルおよび XML プロパティは、ASP.NET 内の埋め込みコードではサポートされません</span><span class="sxs-lookup"><span data-stu-id="faef5-102">XML literals and XML properties are not supported in embedded code within ASP.NET</span></span>
<span data-ttu-id="faef5-103">XML リテラルおよび XML プロパティは、ASP.NET 内の埋め込みコードではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="faef5-103">XML literals and XML properties are not supported in embedded code within ASP.NET.</span></span> <span data-ttu-id="faef5-104">XML 機能を使用するには、コードをコードビハインドに移動します。</span><span class="sxs-lookup"><span data-stu-id="faef5-104">To use XML features, move the code to code-behind.</span></span>  
  
 <span data-ttu-id="faef5-105">XML リテラルまたは XML 軸プロパティは、ASP.NET ファイルの埋め込みコード (`<%= =>`) 内で定義されます。</span><span class="sxs-lookup"><span data-stu-id="faef5-105">An XML literal or XML axis property is defined within embedded code (`<%= =>`) in an ASP.NET file.</span></span>  
  
 <span data-ttu-id="faef5-106">**エラー ID:** BC31200</span><span class="sxs-lookup"><span data-stu-id="faef5-106">**Error ID:** BC31200</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="faef5-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="faef5-107">To correct this error</span></span>  
  
- <span data-ttu-id="faef5-108">XML リテラルまたは XML 軸プロパティが含まれているコードを、ASP.NET 分離コード ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="faef5-108">Move the code that includes the XML literal or XML axis property to an ASP.NET code-behind file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faef5-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="faef5-109">See also</span></span>

- [<span data-ttu-id="faef5-110">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="faef5-110">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="faef5-111">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="faef5-111">XML Axis Properties</span></span>](../xml-axis/index.md)
- [<span data-ttu-id="faef5-112">XML</span><span class="sxs-lookup"><span data-stu-id="faef5-112">XML</span></span>](../../programming-guide/language-features/xml/index.md)
