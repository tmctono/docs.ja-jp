---
title: ICorPublishProcessEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type:
- apiref
ms.openlocfilehash: d79b642735543ff84f6211fe5ca2e5b424be1f2e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103442"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="202cb-102">ICorPublishProcessEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="202cb-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="202cb-103">現在のカーソル位置から開始して、指定した数のプロセスをコレクションから取得します。</span><span class="sxs-lookup"><span data-stu-id="202cb-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="202cb-104">構文</span><span class="sxs-lookup"><span data-stu-id="202cb-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="202cb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="202cb-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="202cb-106">から取得するプロセスの数。</span><span class="sxs-lookup"><span data-stu-id="202cb-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="202cb-107">入出力取得された[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)オブジェクトの配列へのポインター。それぞれがプロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="202cb-107">[out] A pointer to the array of retrieved [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="202cb-108">入出力実際に返されたプロセスの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="202cb-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="202cb-109">`celt` が1の場合、この値は null になります。</span><span class="sxs-lookup"><span data-stu-id="202cb-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="202cb-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="202cb-110">Requirements</span></span>  
 <span data-ttu-id="202cb-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="202cb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="202cb-112">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="202cb-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="202cb-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="202cb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="202cb-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="202cb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="202cb-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="202cb-115">See also</span></span>

- [<span data-ttu-id="202cb-116">ICorPublishProcessEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="202cb-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)
