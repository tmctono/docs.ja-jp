---
title: ICorDebugType::GetClass メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0915027ce6a3768ff854eafc5496c5057081cc4d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499538"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="50299-102">ICorDebugType::GetClass メソッド</span><span class="sxs-lookup"><span data-stu-id="50299-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="50299-103">インスタンス化されていないジェネリック型を表す、ICorDebugClass インターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="50299-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50299-104">構文</span><span class="sxs-lookup"><span data-stu-id="50299-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50299-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="50299-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="50299-106">[out]アドレスへのポインター、`ICorDebugClass`インスタンス化されていないジェネリック型を表すインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="50299-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50299-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="50299-107">Remarks</span></span>  
 <span data-ttu-id="50299-108">`GetClass` 特定の条件下でのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="50299-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="50299-109">呼び出す[icordebugtype::gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)呼び出す前に`GetClass`します。</span><span class="sxs-lookup"><span data-stu-id="50299-109">Call [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="50299-110">場合`ICorDebugType::GetType`ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE、CorElementType 値を返します`GetClass`呼び出すジェネリック型のインスタンス化されていない型を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="50299-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50299-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="50299-111">Requirements</span></span>  
 <span data-ttu-id="50299-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="50299-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50299-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50299-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50299-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50299-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50299-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50299-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
