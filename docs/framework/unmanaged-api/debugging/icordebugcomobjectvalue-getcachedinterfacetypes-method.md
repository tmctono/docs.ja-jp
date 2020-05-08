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
ms.openlocfilehash: 6b02657012870de4d0f888f6c05b115b25073fa2
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892834"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="cfa55-102">ICorDebugComObjectValue::GetCachedInterfaceTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="cfa55-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="cfa55-103">現在のオブジェクトがキャストされた、またはとして使用されたインターフェイス型の列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="cfa55-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfa55-104">構文</span><span class="sxs-lookup"><span data-stu-id="cfa55-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfa55-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cfa55-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="cfa55-106">からメソッドが、ランタイム呼び出し可能ラッパー (RCW) によっ`IInspectable`てキャッシュされた Windows ランタイムインターフェイス (インターフェイス) またはすべての COM インターフェイスだけを返すかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="cfa55-106">[in] A value that indicates whether the method returns only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="cfa55-107">入出力に`bIInspectableOnly`従ってフィルター処理された、キャッシュされたインターフェイスの種類を表す、の型のオブジェクトへのアクセスを提供する、、の各型のオブジェクトへのアクセスを提供する、テキストを指すポインターです。</span><span class="sxs-lookup"><span data-stu-id="cfa55-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfa55-108">解説</span><span class="sxs-lookup"><span data-stu-id="cfa55-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfa55-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="cfa55-109">Requirements</span></span>  
 <span data-ttu-id="cfa55-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfa55-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfa55-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cfa55-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cfa55-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfa55-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfa55-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfa55-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfa55-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfa55-114">See also</span></span>

- [<span data-ttu-id="cfa55-115">ICorDebugComObjectValue のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="cfa55-115">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="cfa55-116">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="cfa55-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
