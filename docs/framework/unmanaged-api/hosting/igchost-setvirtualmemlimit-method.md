---
title: IGCHost::SetVirtualMemLimit メソッド
ms.date: 03/30/2017
api_name:
- IGCHost.SetVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetVirtualMemLimit
helpviewer_keywords:
- IGCHost::SetVirtualMemLimit method [.NET Framework hosting]
- SetVirtualMemLimit method [.NET Framework hosting]
ms.assetid: c7e7c2d0-e58c-4650-b40c-47b2be2cda45
topic_type:
- apiref
ms.openlocfilehash: 93ed63b4abacce1d8943434965aacf67190631b6
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805186"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="eaa7a-102">IGCHost::SetVirtualMemLimit メソッド</span><span class="sxs-lookup"><span data-stu-id="eaa7a-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="eaa7a-103">ランタイムの仮想メモリの最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="eaa7a-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaa7a-104">構文</span><span class="sxs-lookup"><span data-stu-id="eaa7a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eaa7a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eaa7a-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="eaa7a-106">からランタイムの仮想メモリの最大サイズ (mb 単位)。</span><span class="sxs-lookup"><span data-stu-id="eaa7a-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eaa7a-107">解説</span><span class="sxs-lookup"><span data-stu-id="eaa7a-107">Remarks</span></span>  
 <span data-ttu-id="eaa7a-108">ランタイムの仮想メモリの最大サイズは動的に変更できます。</span><span class="sxs-lookup"><span data-stu-id="eaa7a-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaa7a-109">要件</span><span class="sxs-lookup"><span data-stu-id="eaa7a-109">Requirements</span></span>  
 <span data-ttu-id="eaa7a-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaa7a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaa7a-111">**ヘッダー:** GCHost、GCHost</span><span class="sxs-lookup"><span data-stu-id="eaa7a-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="eaa7a-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="eaa7a-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eaa7a-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaa7a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaa7a-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="eaa7a-114">See also</span></span>

- [<span data-ttu-id="eaa7a-115">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eaa7a-115">IGCHost Interface</span></span>](igchost-interface.md)
