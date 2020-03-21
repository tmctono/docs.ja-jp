---
title: ICorDebugProcess5::GetObject メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetObject method [.NET Framework debugging]
ms.assetid: c8111502-5a20-447f-9dc2-76e8acd7ed5a
topic_type:
- apiref
ms.openlocfilehash: 4b48132ee60bcaebb218d8f583de6558372f5055
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178605"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="450ad-102">ICorDebugProcess5::GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="450ad-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="450ad-103">オブジェクト アドレスを "ICorDebugObjectValue" オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="450ad-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="450ad-104">構文</span><span class="sxs-lookup"><span data-stu-id="450ad-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="450ad-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="450ad-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="450ad-106">[in]オブジェクト アドレス。</span><span class="sxs-lookup"><span data-stu-id="450ad-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="450ad-107">[アウト]オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="450ad-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="450ad-108">解説</span><span class="sxs-lookup"><span data-stu-id="450ad-108">Remarks</span></span>  
 <span data-ttu-id="450ad-109">有効`addr`なマネージ オブジェクトを指していない場合、メソッド`GetObject`は`E_FAIL`を返します。</span><span class="sxs-lookup"><span data-stu-id="450ad-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="450ad-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="450ad-110">Requirements</span></span>  
 <span data-ttu-id="450ad-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="450ad-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="450ad-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="450ad-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="450ad-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="450ad-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="450ad-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="450ad-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="450ad-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="450ad-115">See also</span></span>

- [<span data-ttu-id="450ad-116">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="450ad-116">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="450ad-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="450ad-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
