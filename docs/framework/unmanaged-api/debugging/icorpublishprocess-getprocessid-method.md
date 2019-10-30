---
title: ICorPublishProcess::GetProcessID メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetProcessID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type:
- apiref
ms.openlocfilehash: 728e8bdbce7f93176324d8f80261030f8cbae283
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140412"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="3c8c4-102">ICorPublishProcess::GetProcessID メソッド</span><span class="sxs-lookup"><span data-stu-id="3c8c4-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="3c8c4-103">このプロセスのオペレーティングシステム識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c8c4-104">構文</span><span class="sxs-lookup"><span data-stu-id="3c8c4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c8c4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3c8c4-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="3c8c4-106">入出力この[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)オブジェクトによって表されるプロセスの識別子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c8c4-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="3c8c4-107">Requirements</span></span>  
 <span data-ttu-id="3c8c4-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c8c4-109">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="3c8c4-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3c8c4-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c8c4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c8c4-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c8c4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c8c4-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c8c4-112">See also</span></span>

- [<span data-ttu-id="3c8c4-113">ICorPublishProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3c8c4-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
