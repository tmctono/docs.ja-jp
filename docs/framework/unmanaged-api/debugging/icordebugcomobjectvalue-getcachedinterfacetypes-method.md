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
ms.openlocfilehash: f720b06581ac60c8bd68dc5e85f15843fd9425f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788903"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="221cc-102">ICorDebugComObjectValue::GetCachedInterfaceTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="221cc-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="221cc-103">現在のオブジェクトがキャストされた、またはとして使用されたインターフェイス型の列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="221cc-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="221cc-104">構文</span><span class="sxs-lookup"><span data-stu-id="221cc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="221cc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="221cc-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="221cc-106">からメソッドが、ランタイム呼び出し可能ラッパー (RCW) によってキャッシュされた Windows ランタイムインターフェイス (`IInspectable` インターフェイス) またはすべての COM インターフェイスだけを返すかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="221cc-106">[in] A value that indicates whether the method returns only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="221cc-107">入出力`bIInspectableOnly`に従ってフィルター処理された、キャッシュされたインターフェイスの種類を表す、の型のオブジェクトへのアクセスを提供する、の型のオブジェクトへのアクセスを提供する、の型のアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="221cc-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="221cc-108">コメント</span><span class="sxs-lookup"><span data-stu-id="221cc-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="221cc-109">要件</span><span class="sxs-lookup"><span data-stu-id="221cc-109">Requirements</span></span>  
 <span data-ttu-id="221cc-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="221cc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="221cc-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="221cc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="221cc-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="221cc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="221cc-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="221cc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="221cc-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="221cc-114">See also</span></span>

- [<span data-ttu-id="221cc-115">ICorDebugComObjectValue のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="221cc-115">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="221cc-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="221cc-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
