---
title: SaveToHistory 関数-WPF アンマネージ API リファレンス
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- SaveToHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: 6dd101a3-44ad-4143-b228-772156f9b8ff
ms.openlocfilehash: 7337e5dc23a3dce5de8270902bce228c49bc6edb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731750"
---
# <a name="savetohistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="4220b-102">SaveToHistory 関数 (WPF アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="4220b-102">SaveToHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="4220b-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="4220b-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="4220b-104">Windows management の Windows Presentation Foundation (WPF) インフラストラクチャで使用されます。</span><span class="sxs-lookup"><span data-stu-id="4220b-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4220b-105">構文</span><span class="sxs-lookup"><span data-stu-id="4220b-105">Syntax</span></span>  
  
```cpp  
HRESULT SaveToHistory(  
   __in_ecount(1) IStream* pHistoryStream  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="4220b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4220b-106">Parameters</span></span>  
 <span data-ttu-id="4220b-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="4220b-107">pHistoryStream</span></span>  
 <span data-ttu-id="4220b-108">履歴ストリームへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4220b-108">A pointer to the history stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4220b-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="4220b-109">Requirements</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4220b-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="4220b-110">Requirements</span></span>  
 <span data-ttu-id="4220b-111">**プラットフォーム:** 「 [.NET Framework のシステム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4220b-111">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4220b-112">**DLL**</span><span class="sxs-lookup"><span data-stu-id="4220b-112">**DLL:**</span></span>  
  
 <span data-ttu-id="4220b-113">.NET Framework 3.0 と 3.5: プレゼンテーション Hostdll .dll</span><span class="sxs-lookup"><span data-stu-id="4220b-113">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="4220b-114">.NET Framework 4 以降: PresentationHost_v0400 .dll</span><span class="sxs-lookup"><span data-stu-id="4220b-114">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="4220b-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4220b-115">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4220b-116">参照</span><span class="sxs-lookup"><span data-stu-id="4220b-116">See also</span></span>

- [<span data-ttu-id="4220b-117">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="4220b-117">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
