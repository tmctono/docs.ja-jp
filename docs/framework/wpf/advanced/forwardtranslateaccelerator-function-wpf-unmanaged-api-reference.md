---
title: ForwardTranslateAccelerator 関数-WPF アンマネージ API リファレンス
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: f6e8208ffe2c186234f30f31e346ca6b1d0be4c0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747038"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="6a3b1-102">ForwardTranslateAccelerator 関数 (WPF アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="6a3b1-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="6a3b1-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="6a3b1-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="6a3b1-104">Windows management の Windows Presentation Foundation (WPF) インフラストラクチャで使用されます。</span><span class="sxs-lookup"><span data-stu-id="6a3b1-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a3b1-105">構文</span><span class="sxs-lookup"><span data-stu-id="6a3b1-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a3b1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6a3b1-106">Parameters</span></span>  
 <span data-ttu-id="6a3b1-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="6a3b1-107">pMsg</span></span>  
 <span data-ttu-id="6a3b1-108">メッセージへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6a3b1-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="6a3b1-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="6a3b1-109">appUnhandled</span></span>  
 <span data-ttu-id="6a3b1-110">アプリに既に入力メッセージを処理する機会が与えられているが、処理されていない場合は、`true` ます。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="6a3b1-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a3b1-111">要件</span><span class="sxs-lookup"><span data-stu-id="6a3b1-111">Requirements</span></span>  
 <span data-ttu-id="6a3b1-112">**プラットフォーム:** 「 [.NET Framework のシステム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a3b1-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a3b1-113">**DLL**</span><span class="sxs-lookup"><span data-stu-id="6a3b1-113">**DLL:**</span></span>  
  
 <span data-ttu-id="6a3b1-114">.NET Framework 3.0 と 3.5: プレゼンテーション Hostdll .dll</span><span class="sxs-lookup"><span data-stu-id="6a3b1-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="6a3b1-115">.NET Framework 4 以降: PresentationHost_v0400 .dll</span><span class="sxs-lookup"><span data-stu-id="6a3b1-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="6a3b1-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a3b1-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a3b1-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a3b1-117">See also</span></span>

- [<span data-ttu-id="6a3b1-118">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="6a3b1-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
