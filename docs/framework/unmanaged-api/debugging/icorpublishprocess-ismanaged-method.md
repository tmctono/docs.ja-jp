---
title: ICorPublishProcess::IsManaged メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
ms.openlocfilehash: ad3a357a98cb5ed28a34e4076b5e145903ceaf91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103499"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="f1d6d-102">ICorPublishProcess::IsManaged メソッド</span><span class="sxs-lookup"><span data-stu-id="f1d6d-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="f1d6d-103">この[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)によって参照されるプロセスに、マネージコードがあることがわかっているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1d6d-104">構文</span><span class="sxs-lookup"><span data-stu-id="f1d6d-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1d6d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1d6d-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="f1d6d-106">入出力プロセスにマネージコードがあるかどうかを示すブール値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="f1d6d-107">プロセスにマネージコードが含まれている場合、値は `true` です。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1d6d-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1d6d-108">Remarks</span></span>  
 <span data-ttu-id="f1d6d-109">現在のバージョンの `ICorPublishProcess` では、マネージコードを持つプロセスのみにアクセスが許可されるため、`IsManaged` は常に `true`を返します。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1d6d-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="f1d6d-110">Requirements</span></span>  
 <span data-ttu-id="f1d6d-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1d6d-112">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="f1d6d-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f1d6d-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1d6d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1d6d-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1d6d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1d6d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1d6d-115">See also</span></span>

- [<span data-ttu-id="f1d6d-116">ICorPublishProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1d6d-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
