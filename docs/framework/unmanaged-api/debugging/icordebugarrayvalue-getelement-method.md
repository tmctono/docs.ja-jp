---
title: ICorDebugArrayValue::GetElement メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElement
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElement
helpviewer_keywords:
- GetElement method [.NET Framework debugging]
- ICorDebugArrayValue::GetElement method [.NET Framework debugging]
ms.assetid: 7ac3cba5-c282-402e-b7ef-b46634f5176b
topic_type:
- apiref
ms.openlocfilehash: 7a52e61f41bd1d7f68523dd16f70010ffbba401e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895033"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="15d81-102">ICorDebugArrayValue::GetElement メソッド</span><span class="sxs-lookup"><span data-stu-id="15d81-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="15d81-103">指定された配列要素の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="15d81-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15d81-104">構文</span><span class="sxs-lookup"><span data-stu-id="15d81-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15d81-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15d81-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="15d81-106">からこの`ICorDebugArrayValue`オブジェクトの次元数。</span><span class="sxs-lookup"><span data-stu-id="15d81-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="15d81-107">この値は、 `indices`配列のサイズが`ICorDebugArrayValue`オブジェクトの次元数と同じであるため、配列のサイズでもあります。</span><span class="sxs-lookup"><span data-stu-id="15d81-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="15d81-108">からインデックス値の配列。それぞれが`ICorDebugArrayValue`オブジェクトのディメンション内の位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="15d81-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="15d81-109">この値を null にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="15d81-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="15d81-110">入出力指定した要素の値を表す ICorDebugValue オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="15d81-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15d81-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="15d81-111">Requirements</span></span>  
 <span data-ttu-id="15d81-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15d81-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15d81-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15d81-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15d81-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15d81-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15d81-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15d81-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
