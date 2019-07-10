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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c43c2259d5b899f05e42437aa121dde57ce4b0c8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766485"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="b9b1f-102">IGCHost::SetVirtualMemLimit メソッド</span><span class="sxs-lookup"><span data-stu-id="b9b1f-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="b9b1f-103">ランタイムの仮想メモリの最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="b9b1f-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9b1f-104">構文</span><span class="sxs-lookup"><span data-stu-id="b9b1f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9b1f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9b1f-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="b9b1f-106">[in]ランタイムの仮想メモリのメガバイト単位で最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="b9b1f-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9b1f-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="b9b1f-107">Remarks</span></span>  
 <span data-ttu-id="b9b1f-108">ランタイムの仮想メモリの最大サイズを動的に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b9b1f-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9b1f-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="b9b1f-109">Requirements</span></span>  
 <span data-ttu-id="b9b1f-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9b1f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9b1f-111">**ヘッダー:** GCHost.idl、GCHost.h</span><span class="sxs-lookup"><span data-stu-id="b9b1f-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="b9b1f-112">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="b9b1f-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9b1f-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9b1f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9b1f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9b1f-114">See also</span></span>

- [<span data-ttu-id="b9b1f-115">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b9b1f-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
