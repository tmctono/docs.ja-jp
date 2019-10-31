---
title: クラス '<classname>' の情報を読み込めません。
ms.date: 07/20/2015
f1_keywords:
- vbc30712
- bc30712
helpviewer_keywords:
- BC30712
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
ms.openlocfilehash: b3ef2aa5e25d61f005159e06852e23c2c036fd54
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198177"
---
# <a name="unable-to-load-information-for-class-classname"></a><span data-ttu-id="9f8fa-102">クラス '\<classname > ' の情報を読み込めません</span><span class="sxs-lookup"><span data-stu-id="9f8fa-102">Unable to load information for class '\<classname>'</span></span>
<span data-ttu-id="9f8fa-103">使用できないクラスへの参照が作成されました。</span><span class="sxs-lookup"><span data-stu-id="9f8fa-103">A reference was made to a class that is not available.</span></span>  
  
 <span data-ttu-id="9f8fa-104">**エラー ID:** BC30712</span><span class="sxs-lookup"><span data-stu-id="9f8fa-104">**Error ID:** BC30712</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9f8fa-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="9f8fa-105">To correct this error</span></span>  
  
1. <span data-ttu-id="9f8fa-106">クラスが定義されていること、および名前のスペルが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9f8fa-106">Verify that the class is defined and that you spelled the name correctly.</span></span>  
  
2. <span data-ttu-id="9f8fa-107">モジュールで宣言されたいずれかのメンバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9f8fa-107">Try accessing one of the members declared in the module.</span></span> <span data-ttu-id="9f8fa-108">宣言されているモジュールがまだ読み込まれていないために、デバッグ環境ではメンバーを特定できないという場合もあります。</span><span class="sxs-lookup"><span data-stu-id="9f8fa-108">In some cases, the debugging environment cannot locate members because the modules where they are declared have not been loaded yet.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f8fa-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f8fa-109">See also</span></span>

- [<span data-ttu-id="9f8fa-110">Visual Studio でのデバッグ</span><span class="sxs-lookup"><span data-stu-id="9f8fa-110">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
