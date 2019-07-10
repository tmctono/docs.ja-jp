---
title: Icordebugtype 2::gettypeid メソッド
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3098911bab2878876b93ee1ce23d9794d7e6cdbd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772471"
---
# <a name="icordebugtype2gettypeid-method"></a><span data-ttu-id="6913f-102">Icordebugtype 2::gettypeid メソッド</span><span class="sxs-lookup"><span data-stu-id="6913f-102">ICorDebugType2::GetTypeID Method</span></span>
<span data-ttu-id="6913f-103">取得、 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)この種類。</span><span class="sxs-lookup"><span data-stu-id="6913f-103">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6913f-104">構文</span><span class="sxs-lookup"><span data-stu-id="6913f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6913f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6913f-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="6913f-106">[out]ポインター、 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)この icordebugtype します。</span><span class="sxs-lookup"><span data-stu-id="6913f-106">[out] A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this ICorDebugType.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6913f-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="6913f-107">Return Value</span></span>  
 <span data-ttu-id="6913f-108">戻り値は、成功の場合は `S_OK` で、失敗の場合は `HRESULT` コードです。</span><span class="sxs-lookup"><span data-stu-id="6913f-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="6913f-109">`HRESULT`コードには、次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6913f-109">The `HRESULT` codes include the following:</span></span>  
  
|<span data-ttu-id="6913f-110">リターン コード</span><span class="sxs-lookup"><span data-stu-id="6913f-110">Return code</span></span>|<span data-ttu-id="6913f-111">説明</span><span class="sxs-lookup"><span data-stu-id="6913f-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="6913f-112">メソッドが成功しました。</span><span class="sxs-lookup"><span data-stu-id="6913f-112">Method succeeded.</span></span> <span data-ttu-id="6913f-113">メソッドは、有効な取得が[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)します。</span><span class="sxs-lookup"><span data-stu-id="6913f-113">The method has retrieved a valid [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md).</span></span>|  
|`CORDBG_E_CLASS_NOT_LOADED`|<span data-ttu-id="6913f-114">型が読み込まれていません。</span><span class="sxs-lookup"><span data-stu-id="6913f-114">The type has not been loaded.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="6913f-115">型がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6913f-115">The type is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6913f-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="6913f-116">Remarks</span></span>  
 <span data-ttu-id="6913f-117">このメソッドでは、マッピングを提供することがありますいないに読み込まれている、実行時に、型を表す、ICorDebugType から、 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)ランタイムに読み込まれた型を識別する非透過的なとして機能する処理です。</span><span class="sxs-lookup"><span data-stu-id="6913f-117">This method provides a mapping from the ICorDebugType, which represents a type that may or may not have been loaded into the runtime, to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which serves as an opaque handle that identifies a type loaded into the runtime.</span></span>  
  
 <span data-ttu-id="6913f-118">ときに、ICorDebugType を表す型がまだ読み込まれていますが、このメソッドが戻る`CORDBG_E_CLASS_NOT_LOADED`します。</span><span class="sxs-lookup"><span data-stu-id="6913f-118">When the type that the ICorDebugType represents has not yet been loaded, this method returns `CORDBG_E_CLASS_NOT_LOADED`.</span></span>  <span data-ttu-id="6913f-119">返すかどうか、型はサポートされていません、`CORDBG_E_UNSUPPORTED`します。</span><span class="sxs-lookup"><span data-stu-id="6913f-119">If the type is not supported, it returns `CORDBG_E_UNSUPPORTED`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6913f-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="6913f-120">Requirements</span></span>  
 <span data-ttu-id="6913f-121">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6913f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6913f-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6913f-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6913f-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6913f-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6913f-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6913f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6913f-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="6913f-125">See also</span></span>

- [<span data-ttu-id="6913f-126">ICorDebugType2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6913f-126">ICorDebugType2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)
