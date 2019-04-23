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
ms.openlocfilehash: 169716d1a6d0dd633821cc832de96c9a02958d76
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183106"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="a66df-102">ICorPublishProcessEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="a66df-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="a66df-103">現在のカーソル位置から、コレクションから指定されたプロセスの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="a66df-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a66df-104">構文</span><span class="sxs-lookup"><span data-stu-id="a66df-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a66df-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a66df-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a66df-106">[in]取得するプロセスの数。</span><span class="sxs-lookup"><span data-stu-id="a66df-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="a66df-107">[out]配列へのポインターの取得[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)プロセスを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a66df-107">[out] A pointer to the array of retrieved [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a66df-108">[out]プロセスの数へのポインターが実際に返されます。</span><span class="sxs-lookup"><span data-stu-id="a66df-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="a66df-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="a66df-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a66df-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="a66df-110">Requirements</span></span>  
 <span data-ttu-id="a66df-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a66df-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a66df-112">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="a66df-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="a66df-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a66df-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a66df-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a66df-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a66df-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a66df-115">See also</span></span>

- [<span data-ttu-id="a66df-116">ICorPublishProcessEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a66df-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)
