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
ms.openlocfilehash: 29427bab938437c40d0edb5676a2f8f76cbb6691
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764865"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="9f134-102">ICorPublishProcess::GetProcessID メソッド</span><span class="sxs-lookup"><span data-stu-id="9f134-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="9f134-103">このプロセスには、オペレーティング システムの識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="9f134-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f134-104">構文</span><span class="sxs-lookup"><span data-stu-id="9f134-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f134-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9f134-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="9f134-106">[out]これで表されるプロセスの id へのポインター [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9f134-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f134-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="9f134-107">Requirements</span></span>  
 <span data-ttu-id="9f134-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f134-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f134-109">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="9f134-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="9f134-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f134-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f134-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f134-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f134-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f134-112">See also</span></span>

- [<span data-ttu-id="9f134-113">ICorPublishProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f134-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
