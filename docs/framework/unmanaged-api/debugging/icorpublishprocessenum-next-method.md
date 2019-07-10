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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 40a6376d4f4ffd09743441df1965d0a0f0d969b9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764843"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="70d2b-102">ICorPublishProcessEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="70d2b-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="70d2b-103">現在のカーソル位置から、コレクションから指定されたプロセスの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="70d2b-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70d2b-104">構文</span><span class="sxs-lookup"><span data-stu-id="70d2b-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70d2b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="70d2b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="70d2b-106">[in]取得するプロセスの数。</span><span class="sxs-lookup"><span data-stu-id="70d2b-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="70d2b-107">[out]配列へのポインターの取得[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)プロセスを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="70d2b-107">[out] A pointer to the array of retrieved [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="70d2b-108">[out]プロセスの数へのポインターが実際に返されます。</span><span class="sxs-lookup"><span data-stu-id="70d2b-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="70d2b-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="70d2b-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70d2b-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="70d2b-110">Requirements</span></span>  
 <span data-ttu-id="70d2b-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="70d2b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70d2b-112">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="70d2b-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="70d2b-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70d2b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70d2b-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70d2b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70d2b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="70d2b-115">See also</span></span>

- [<span data-ttu-id="70d2b-116">ICorPublishProcessEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70d2b-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)
