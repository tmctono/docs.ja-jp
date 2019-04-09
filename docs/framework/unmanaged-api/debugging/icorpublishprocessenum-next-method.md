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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183106"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="34294-102">ICorPublishProcessEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="34294-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="34294-103">現在のカーソル位置から、コレクションから指定されたプロセスの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="34294-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34294-104">構文</span><span class="sxs-lookup"><span data-stu-id="34294-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34294-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="34294-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="34294-106">[in]取得するプロセスの数。</span><span class="sxs-lookup"><span data-stu-id="34294-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="34294-107">[out]配列へのポインターの取得[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)プロセスを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="34294-107">[out] A pointer to the array of retrieved [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="34294-108">[out]プロセスの数へのポインターが実際に返されます。</span><span class="sxs-lookup"><span data-stu-id="34294-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="34294-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="34294-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34294-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="34294-110">Requirements</span></span>  
 <span data-ttu-id="34294-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="34294-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34294-112">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="34294-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="34294-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34294-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="34294-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="34294-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="34294-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="34294-115">See also</span></span>

- [<span data-ttu-id="34294-116">ICorPublishProcessEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34294-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)
