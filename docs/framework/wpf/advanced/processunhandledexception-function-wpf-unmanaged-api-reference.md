---
title: ProcessUnhandledException 関数-WPF アンマネージ API リファレンス
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 757e5ac3aa2dc4c87b210b026998523bd82045c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743921"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="2fa14-102">ProcessUnhandledException 関数 (WPF アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="2fa14-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="2fa14-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="2fa14-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="2fa14-104">例外処理のために Windows Presentation Foundation (WPF) インフラストラクチャによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="2fa14-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fa14-105">構文</span><span class="sxs-lookup"><span data-stu-id="2fa14-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fa14-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2fa14-106">Parameters</span></span>  
 <span data-ttu-id="2fa14-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="2fa14-107">errorMsg</span></span>  
 <span data-ttu-id="2fa14-108">エラー メッセージです。</span><span class="sxs-lookup"><span data-stu-id="2fa14-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fa14-109">要件</span><span class="sxs-lookup"><span data-stu-id="2fa14-109">Requirements</span></span>  
 <span data-ttu-id="2fa14-110">**プラットフォーム:** 「 [.NET Framework のシステム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fa14-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fa14-111">**DLL**</span><span class="sxs-lookup"><span data-stu-id="2fa14-111">**DLL:**</span></span>  
  
 <span data-ttu-id="2fa14-112">.NET Framework 3.0 と 3.5: プレゼンテーション Hostdll .dll</span><span class="sxs-lookup"><span data-stu-id="2fa14-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="2fa14-113">.NET Framework 4 以降: PresentationHost_v0400 .dll</span><span class="sxs-lookup"><span data-stu-id="2fa14-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="2fa14-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fa14-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fa14-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2fa14-115">See also</span></span>

- [<span data-ttu-id="2fa14-116">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="2fa14-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
