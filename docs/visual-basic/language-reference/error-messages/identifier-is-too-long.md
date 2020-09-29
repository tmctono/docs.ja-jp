---
title: 識別子が長すぎます。
ms.date: 07/20/2015
f1_keywords:
- bc30033
- vbc30033
helpviewer_keywords:
- BC30033
ms.assetid: 3d07f6d0-9a2f-49ca-94e8-1e354932e855
ms.openlocfilehash: 084e3d9306ad84d7e6e36e5fe4bbfc868b8dfac6
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874004"
---
# <a name="identifier-is-too-long"></a><span data-ttu-id="46425-102">識別子が長すぎます。</span><span class="sxs-lookup"><span data-stu-id="46425-102">Identifier is too long</span></span>

<span data-ttu-id="46425-103">すべてのプログラミング要素の名前または識別子は、1023 文字に制限されています。</span><span class="sxs-lookup"><span data-stu-id="46425-103">The name, or identifier, of every programming element is limited to 1023 characters.</span></span> <span data-ttu-id="46425-104">さらに、完全修飾名は 1023 文字を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="46425-104">In addition, a fully qualified name cannot exceed 1023 characters.</span></span> <span data-ttu-id="46425-105">つまり、識別子の文字列全体 (`<namespace>.<...>.<namespace>.<class>.<element>`) で、メンバーアクセス演算子 (`.`) 文字を含めて、1023 文字の長さを超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="46425-105">This means that the entire identifier string (`<namespace>.<...>.<namespace>.<class>.<element>`) cannot be more than 1023 characters long, including the member-access operator (`.`) characters.</span></span>  
  
 <span data-ttu-id="46425-106">**エラー ID:** BC30033</span><span class="sxs-lookup"><span data-stu-id="46425-106">**Error ID:** BC30033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="46425-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="46425-107">To correct this error</span></span>  
  
- <span data-ttu-id="46425-108">識別子の長さを短くします。</span><span class="sxs-lookup"><span data-stu-id="46425-108">Reduce the length of the identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46425-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="46425-109">See also</span></span>

- [<span data-ttu-id="46425-110">宣言された要素の名前</span><span class="sxs-lookup"><span data-stu-id="46425-110">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
