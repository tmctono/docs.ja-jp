---
title: ForwardTranslateAccelerator 関数 (WPF のアンマネージ API リファレンス)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: 4bb7e665bb836dc5f95b14f39179f1d4b9f8173d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080255"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="6ceb5-102">ForwardTranslateAccelerator 関数 (WPF のアンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="6ceb5-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="6ceb5-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートしているし、コードから直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="6ceb5-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="6ceb5-104">Windows Presentation Foundation (WPF) インフラストラクチャによって windows の管理に使用します。</span><span class="sxs-lookup"><span data-stu-id="6ceb5-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ceb5-105">構文</span><span class="sxs-lookup"><span data-stu-id="6ceb5-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ceb5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6ceb5-106">Parameters</span></span>  
 <span data-ttu-id="6ceb5-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="6ceb5-107">pMsg</span></span>  
 <span data-ttu-id="6ceb5-108">メッセージへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6ceb5-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="6ceb5-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="6ceb5-109">appUnhandled</span></span>  
 <span data-ttu-id="6ceb5-110">`true` アプリが、入力メッセージを処理する機会が与えられた既にがそれを処理していません。それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="6ceb5-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ceb5-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="6ceb5-111">Requirements</span></span>  
 <span data-ttu-id="6ceb5-112">**プラットフォーム:** 参照してください[.NET Framework システム要件](../../get-started/system-requirements.md)します。</span><span class="sxs-lookup"><span data-stu-id="6ceb5-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ceb5-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="6ceb5-113">**DLL:**</span></span>  
  
 <span data-ttu-id="6ceb5-114">.NET framework 3.0 および 3.5。PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="6ceb5-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="6ceb5-115">.NET framework 4 以降では。PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="6ceb5-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="6ceb5-116">**.NET framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ceb5-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ceb5-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ceb5-117">See also</span></span>

- [<span data-ttu-id="6ceb5-118">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="6ceb5-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
