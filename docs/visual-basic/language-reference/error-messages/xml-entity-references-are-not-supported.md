---
title: XML エンティティの参照はサポートされていません
ms.date: 07/20/2015
f1_keywords:
- vbc31180
- bc31180
helpviewer_keywords:
- BC31180
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
ms.openlocfilehash: 470e5577654ce8b6bbc2732a41c130a85ddc96e5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874988"
---
# <a name="xml-entity-references-are-not-supported"></a><span data-ttu-id="f84f1-102">XML エンティティの参照はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="f84f1-102">XML entity references are not supported</span></span>

<span data-ttu-id="f84f1-103">XML 1.0 仕様で定義されていないエンティティ参照 (`©` など) が、XML リテラルの値として含まれています。</span><span class="sxs-lookup"><span data-stu-id="f84f1-103">An entity reference (for example, `©`) that is not defined in the XML 1.0 specification is included as a value for an XML literal.</span></span> <span data-ttu-id="f84f1-104">XML リテラルでは、`&`、`"`、`<`、`>`、および `'` の XML エンティティ参照のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f84f1-104">Only `&`, `"`, `<`, `>`, and `'` XML entity references are supported in XML literals.</span></span>  
  
 <span data-ttu-id="f84f1-105">**エラー ID:** BC31180</span><span class="sxs-lookup"><span data-stu-id="f84f1-105">**Error ID:** BC31180</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f84f1-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="f84f1-106">To correct this error</span></span>  
  
- <span data-ttu-id="f84f1-107">サポートされていないエンティティ参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="f84f1-107">Remove the unsupported entity reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f84f1-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="f84f1-108">See also</span></span>

- [<span data-ttu-id="f84f1-109">XML リテラルと XML 1.0 仕様</span><span class="sxs-lookup"><span data-stu-id="f84f1-109">XML Literals and the XML 1.0 Specification</span></span>](../../programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)
- [<span data-ttu-id="f84f1-110">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="f84f1-110">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="f84f1-111">XML</span><span class="sxs-lookup"><span data-stu-id="f84f1-111">XML</span></span>](../../programming-guide/language-features/xml/index.md)
