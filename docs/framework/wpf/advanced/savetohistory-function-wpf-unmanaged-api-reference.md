---
title: SaveToHistory 関数 - WPF アンマネージ API リファレンス
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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731750"
---
# <a name="savetohistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="134ef-102">SaveToHistory 関数 (WPF アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="134ef-102">SaveToHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="134ef-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートしますが、独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="134ef-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="134ef-104">ウィンドウの管理のために Windows Presentation Foundation (WPF) インフラストラクチャによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="134ef-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="134ef-105">構文</span><span class="sxs-lookup"><span data-stu-id="134ef-105">Syntax</span></span>  
  
```cpp  
HRESULT SaveToHistory(  
   __in_ecount(1) IStream* pHistoryStream  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="134ef-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="134ef-106">Parameters</span></span>  
 <span data-ttu-id="134ef-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="134ef-107">pHistoryStream</span></span>  
 <span data-ttu-id="134ef-108">履歴ストリームへのポインター。</span><span class="sxs-lookup"><span data-stu-id="134ef-108">A pointer to the history stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="134ef-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="134ef-109">Requirements</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="134ef-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="134ef-110">Requirements</span></span>  
 <span data-ttu-id="134ef-111">**プラットフォーム:** 「[.NET Framework システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="134ef-111">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="134ef-112">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="134ef-112">**DLL:**</span></span>  
  
 <span data-ttu-id="134ef-113">.NET Framework 3.0 および 3.5 の場合:PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="134ef-113">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="134ef-114">.NET Framework 4 以降の場合:PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="134ef-114">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="134ef-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="134ef-115">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="134ef-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="134ef-116">See also</span></span>

- [<span data-ttu-id="134ef-117">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="134ef-117">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
