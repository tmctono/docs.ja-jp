---
title: 読み込み履歴関数 - WPF アンマネージ API リファレンス
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: be9b8658614e678b4370044a753554859d230fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141576"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="8369f-102">読み込み履歴関数 (WPF アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="8369f-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="8369f-103">この API は、Windows プレゼンテーション基盤 (WPF) インフラストラクチャをサポートし、コードから直接使用することを意図していません。</span><span class="sxs-lookup"><span data-stu-id="8369f-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="8369f-104">Windows プレゼンテーション ファウンデーション (WPF) インフラストラクチャによってウィンドウ管理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8369f-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8369f-105">構文</span><span class="sxs-lookup"><span data-stu-id="8369f-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="8369f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8369f-106">Parameters</span></span>  
 <span data-ttu-id="8369f-107">をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8369f-107">pHistoryStream</span></span>  
 <span data-ttu-id="8369f-108">履歴情報のストリームへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8369f-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="8369f-109">をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8369f-109">pBindCtx</span></span>  
 <span data-ttu-id="8369f-110">バインド コンテキストへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8369f-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8369f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="8369f-111">Requirements</span></span>  
 <span data-ttu-id="8369f-112">**プラットフォーム:**[NET Framework のシステム要件](../../get-started/system-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8369f-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8369f-113">**Dll：**</span><span class="sxs-lookup"><span data-stu-id="8369f-113">**DLL:**</span></span>  
  
 <span data-ttu-id="8369f-114">NET フレームワーク 3.0 および 3.5: プレゼンテーションホストDLL.dll</span><span class="sxs-lookup"><span data-stu-id="8369f-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="8369f-115">NET フレームワーク 4 以降の場合: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="8369f-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="8369f-116">**.NET フレームワーク のバージョン:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8369f-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8369f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="8369f-117">See also</span></span>

- [<span data-ttu-id="8369f-118">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="8369f-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
