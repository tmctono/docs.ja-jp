---
title: LoadFromHistory 関数-WPF アンマネージ API リファレンス
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: 7807e073d1f09ac6a6213aee6d86d53cc75a3c56
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727934"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="e69d8-102">LoadFromHistory 関数 (WPF アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="e69d8-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="e69d8-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="e69d8-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="e69d8-104">Windows management の Windows Presentation Foundation (WPF) インフラストラクチャで使用されます。</span><span class="sxs-lookup"><span data-stu-id="e69d8-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e69d8-105">構文</span><span class="sxs-lookup"><span data-stu-id="e69d8-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="e69d8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e69d8-106">Parameters</span></span>  
 <span data-ttu-id="e69d8-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="e69d8-107">pHistoryStream</span></span>  
 <span data-ttu-id="e69d8-108">履歴情報のストリームへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e69d8-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="e69d8-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="e69d8-109">pBindCtx</span></span>  
 <span data-ttu-id="e69d8-110">バインドコンテキストへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e69d8-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e69d8-111">要件</span><span class="sxs-lookup"><span data-stu-id="e69d8-111">Requirements</span></span>  
 <span data-ttu-id="e69d8-112">**プラットフォーム:** 「 [.NET Framework のシステム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e69d8-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e69d8-113">**DLL**</span><span class="sxs-lookup"><span data-stu-id="e69d8-113">**DLL:**</span></span>  
  
 <span data-ttu-id="e69d8-114">.NET Framework 3.0 と 3.5: プレゼンテーション Hostdll .dll</span><span class="sxs-lookup"><span data-stu-id="e69d8-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="e69d8-115">.NET Framework 4 以降: PresentationHost_v0400 .dll</span><span class="sxs-lookup"><span data-stu-id="e69d8-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="e69d8-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e69d8-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e69d8-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="e69d8-117">See also</span></span>

- [<span data-ttu-id="e69d8-118">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="e69d8-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
