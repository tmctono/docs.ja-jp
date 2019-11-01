---
title: 'ICorDebugType2:: GetTypeID メソッド'
ms.date: 03/30/2017
api_name:
- ICorDebugType2.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type:
- apiref
ms.openlocfilehash: 944313893d88b8eff97291d2517e4863a5ae958a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092760"
---
# <a name="icordebugtype2gettypeid-method"></a><span data-ttu-id="8a5b4-102">ICorDebugType2:: GetTypeID メソッド</span><span class="sxs-lookup"><span data-stu-id="8a5b4-102">ICorDebugType2::GetTypeID Method</span></span>
<span data-ttu-id="8a5b4-103">この型の[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)を取得します。</span><span class="sxs-lookup"><span data-stu-id="8a5b4-103">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a5b4-104">構文</span><span class="sxs-lookup"><span data-stu-id="8a5b4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a5b4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8a5b4-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="8a5b4-106">入出力この [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 型のへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8a5b4-106">[out] A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this ICorDebugType.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a5b4-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="8a5b4-107">Return Value</span></span>  
 <span data-ttu-id="8a5b4-108">戻り値は、成功の場合は `S_OK` で、失敗の場合は `HRESULT` コードです。</span><span class="sxs-lookup"><span data-stu-id="8a5b4-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="8a5b4-109">`HRESULT` コードには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8a5b4-109">The `HRESULT` codes include the following:</span></span>  
  
|<span data-ttu-id="8a5b4-110">リターン コード</span><span class="sxs-lookup"><span data-stu-id="8a5b4-110">Return code</span></span>|<span data-ttu-id="8a5b4-111">説明</span><span class="sxs-lookup"><span data-stu-id="8a5b4-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="8a5b4-112">メソッドが成功しました。</span><span class="sxs-lookup"><span data-stu-id="8a5b4-112">Method succeeded.</span></span> <span data-ttu-id="8a5b4-113">メソッドは、有効な[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)を取得しました。</span><span class="sxs-lookup"><span data-stu-id="8a5b4-113">The method has retrieved a valid [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md).</span></span>|  
|`CORDBG_E_CLASS_NOT_LOADED`|<span data-ttu-id="8a5b4-114">型が読み込まれていません。</span><span class="sxs-lookup"><span data-stu-id="8a5b4-114">The type has not been loaded.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="8a5b4-115">この型はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8a5b4-115">The type is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a5b4-116">コメント</span><span class="sxs-lookup"><span data-stu-id="8a5b4-116">Remarks</span></span>  
 <span data-ttu-id="8a5b4-117">このメソッドは、 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)に読み込まれている可能性があるか、またはランタイムに読み込まれていない型を表す、は、ランタイムに読み込まれた型を識別する不透明なハンドルとして機能する、の型からのマッピングを提供します。</span><span class="sxs-lookup"><span data-stu-id="8a5b4-117">This method provides a mapping from the ICorDebugType, which represents a type that may or may not have been loaded into the runtime, to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which serves as an opaque handle that identifies a type loaded into the runtime.</span></span>  
  
 <span data-ttu-id="8a5b4-118">によって表される型がまだ読み込まれていない場合、このメソッドは `CORDBG_E_CLASS_NOT_LOADED`を返します。</span><span class="sxs-lookup"><span data-stu-id="8a5b4-118">When the type that the ICorDebugType represents has not yet been loaded, this method returns `CORDBG_E_CLASS_NOT_LOADED`.</span></span>  <span data-ttu-id="8a5b4-119">型がサポートされていない場合は、`CORDBG_E_UNSUPPORTED`を返します。</span><span class="sxs-lookup"><span data-stu-id="8a5b4-119">If the type is not supported, it returns `CORDBG_E_UNSUPPORTED`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a5b4-120">要件</span><span class="sxs-lookup"><span data-stu-id="8a5b4-120">Requirements</span></span>  
 <span data-ttu-id="8a5b4-121">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a5b4-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a5b4-122">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="8a5b4-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a5b4-123">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="8a5b4-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a5b4-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a5b4-124">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a5b4-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a5b4-125">See also</span></span>

- [<span data-ttu-id="8a5b4-126">ICorDebugType2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a5b4-126">ICorDebugType2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)
