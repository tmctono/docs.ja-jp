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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f3948e45b991e667ea90c7846ee0d6fd630c0db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165803"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="5f1f9-102">ICorPublishProcess::GetProcessID メソッド</span><span class="sxs-lookup"><span data-stu-id="5f1f9-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="5f1f9-103">このプロセスには、オペレーティング システムの識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="5f1f9-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f1f9-104">構文</span><span class="sxs-lookup"><span data-stu-id="5f1f9-104">Syntax</span></span>  
  
```  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f1f9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5f1f9-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="5f1f9-106">[out]これで表されるプロセスの id へのポインター [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5f1f9-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f1f9-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="5f1f9-107">Requirements</span></span>  
 <span data-ttu-id="5f1f9-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f1f9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f1f9-109">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="5f1f9-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="5f1f9-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f1f9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f1f9-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f1f9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f1f9-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f1f9-112">See also</span></span>

- [<span data-ttu-id="5f1f9-113">ICorPublishProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5f1f9-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
