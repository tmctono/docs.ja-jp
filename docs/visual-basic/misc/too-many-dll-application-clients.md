---
title: DLL のクライアント アプリケーションの数が多すぎます
ms.date: 07/20/2015
f1_keywords:
- vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
ms.openlocfilehash: dcac2658b18b753166770ba5b67024fe88b78b45
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078425"
---
# <a name="too-many-dll-application-clients"></a><span data-ttu-id="10995-102">DLL のクライアント アプリケーションの数が多すぎます</span><span class="sxs-lookup"><span data-stu-id="10995-102">Too many DLL application clients</span></span>

<span data-ttu-id="10995-103">Visual Basic のダイナミックリンクライブラリ (DLL) は、限られた数のホストアプリケーションのみによるアクセスに対応できます。</span><span class="sxs-lookup"><span data-stu-id="10995-103">The dynamic-link library (DLL) for Visual Basic can only accommodate access by a limited number of host applications.</span></span> <span data-ttu-id="10995-104">アプリケーションと Visual Basic ホスト (アプリケーションからアクセスできるアプリケーション) がある場合は、すべて同時に Visual Basic DLL にアクセスしようとしています。</span><span class="sxs-lookup"><span data-stu-id="10995-104">Your application and other applications that are Visual Basic hosts (some of which may be accessed by your application) are all attempting to access the Visual Basic DLL at the same time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="10995-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="10995-105">To correct this error</span></span>  
  
- <span data-ttu-id="10995-106">Visual Basic にアクセスする、開いているアプリケーションの数を減らします。</span><span class="sxs-lookup"><span data-stu-id="10995-106">Reduce the number of open applications accessing Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10995-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="10995-107">See also</span></span>

- [<span data-ttu-id="10995-108">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="10995-108">Error Types</span></span>](../programming-guide/language-features/error-types.md)
