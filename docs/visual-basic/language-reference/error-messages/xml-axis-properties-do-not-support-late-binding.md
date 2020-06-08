---
title: XML 軸のプロパティは遅延バインディングをサポートしていません
ms.date: 07/20/2015
f1_keywords:
- bc31168
- vbc31168
helpviewer_keywords:
- BC31168
ms.assetid: 45707363-55e4-4151-892d-d8729106355b
ms.openlocfilehash: 6c263abe7710157338a795639cca8fd73103d47d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406496"
---
# <a name="xml-axis-properties-do-not-support-late-binding"></a><span data-ttu-id="cc63c-102">XML 軸のプロパティは遅延バインディングをサポートしていません</span><span class="sxs-lookup"><span data-stu-id="cc63c-102">XML axis properties do not support late binding</span></span>
<span data-ttu-id="cc63c-103">型指定されていないオブジェクトに対して、XML 軸プロパティが参照されています。</span><span class="sxs-lookup"><span data-stu-id="cc63c-103">An XML axis property has been referenced for an untyped object.</span></span>  
  
 <span data-ttu-id="cc63c-104">**エラー ID:** BC31168</span><span class="sxs-lookup"><span data-stu-id="cc63c-104">**Error ID:** BC31168</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cc63c-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="cc63c-105">To correct this error</span></span>  
  
- <span data-ttu-id="cc63c-106">XML 軸プロパティを参照する前に、オブジェクトが厳密に型指定された <xref:System.Xml.Linq.XElement> オブジェクトであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cc63c-106">Ensure that the object is a strong-typed <xref:System.Xml.Linq.XElement> object before referencing the XML axis property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc63c-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc63c-107">See also</span></span>

- [<span data-ttu-id="cc63c-108">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="cc63c-108">XML Axis Properties</span></span>](../xml-axis/index.md)
- [<span data-ttu-id="cc63c-109">XML</span><span class="sxs-lookup"><span data-stu-id="cc63c-109">XML</span></span>](../../programming-guide/language-features/xml/index.md)
