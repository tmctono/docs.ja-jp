---
title: ForwardTranslateAccelerator 関数 - WPF アンマネージド API リファレンス
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: a0a01be3000dc53df7855cb74015ba1164206838
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186631"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="a8bb6-102">ForwardTranslateAccelerator 関数 (WPF アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="a8bb6-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="a8bb6-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートしますが、独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="a8bb6-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="a8bb6-104">ウィンドウの管理のために Windows Presentation Foundation (WPF) インフラストラクチャによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="a8bb6-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8bb6-105">構文</span><span class="sxs-lookup"><span data-stu-id="a8bb6-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8bb6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a8bb6-106">Parameters</span></span>  
 <span data-ttu-id="a8bb6-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="a8bb6-107">pMsg</span></span>  
 <span data-ttu-id="a8bb6-108">メッセージへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a8bb6-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="a8bb6-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="a8bb6-109">appUnhandled</span></span>  
 <span data-ttu-id="a8bb6-110">アプリは入力メッセージを処理する機会を既に与えられたがメッセージを処理していない場合は `true`。それ以外の場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="a8bb6-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8bb6-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="a8bb6-111">Requirements</span></span>  
 <span data-ttu-id="a8bb6-112">**プラットフォーム:** 「[.NET Framework システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8bb6-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8bb6-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="a8bb6-113">**DLL:**</span></span>  
  
 <span data-ttu-id="a8bb6-114">.NET Framework 3.0 および 3.5 の場合: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="a8bb6-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="a8bb6-115">.NET Framework 4 以降の場合: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="a8bb6-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="a8bb6-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8bb6-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8bb6-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8bb6-117">See also</span></span>

- [<span data-ttu-id="a8bb6-118">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="a8bb6-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
