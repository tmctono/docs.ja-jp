---
ms.openlocfilehash: acd87c6ad5de3621cc90e5f3e1566592a4eb7e46
ms.sourcegitcommit: 5fd80619c760fa8c25d33a6f5661247cb65da465
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50746530"
---

<span data-ttu-id="668f5-101">アンダースコア文字を先頭の区切り記号として使用するには、以下の要素を Visual Basic プロジェクト (\*.vbproj) ファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="668f5-101">To use the underscore character as a leading separator, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="668f5-102">詳細については、[Visual Basic の言語バージョンを設定](../docs/visual-basic/language-reference/configure-language-version.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="668f5-102">For more information see [setting the Visual Basic language version](../docs/visual-basic/language-reference/configure-language-version.md).</span></span>
