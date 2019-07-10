---
title: ICorDebugComObjectValue::GetCachedInterfaceTypes メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c7325e84d8fe4df9a31543426c6376d0941306fd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748458"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="facd6-102">ICorDebugComObjectValue::GetCachedInterfaceTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="facd6-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="facd6-103">現在のオブジェクトにキャストまたはとして使用されていることには、列挙子インターフェイス型を提供します。</span><span class="sxs-lookup"><span data-stu-id="facd6-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="facd6-104">構文</span><span class="sxs-lookup"><span data-stu-id="facd6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="facd6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="facd6-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="facd6-106">[in]メソッドが唯一の Windows ランタイム インターフェイスを返すかどうかを示す値 (`IInspectable`インターフェイス) またはランタイム呼び出し可能ラッパー (RCW) によってキャッシュされたすべての COM インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="facd6-106">[in] A value that indicates whether the method returns only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="facd6-107">[out]キャッシュされたインターフェイス型を表す ICorDebugType オブジェクトへのアクセスを提供する ICorDebugTypeEnum 列挙子のアドレスへのポインターがに従ってフィルター処理された`bIInspectableOnly`します。</span><span class="sxs-lookup"><span data-stu-id="facd6-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="facd6-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="facd6-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="facd6-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="facd6-109">Requirements</span></span>  
 <span data-ttu-id="facd6-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="facd6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="facd6-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="facd6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="facd6-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="facd6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="facd6-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="facd6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="facd6-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="facd6-114">See also</span></span>

- [<span data-ttu-id="facd6-115">ICorDebugComObjectValue のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="facd6-115">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="facd6-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="facd6-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
