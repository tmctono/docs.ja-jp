---
title: ICorDebugModule::GetMetaDataInterface メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5d28118ea1cc26f80ecc67ccedd160447aa69a4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479035"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a><span data-ttu-id="d921b-102">ICorDebugModule::GetMetaDataInterface メソッド</span><span class="sxs-lookup"><span data-stu-id="d921b-102">ICorDebugModule::GetMetaDataInterface Method</span></span>
<span data-ttu-id="d921b-103">モジュールのメタデータの検査に使用できるメタデータ インターフェイス オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="d921b-103">Gets a metadata interface object that can be used to examine the metadata for the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d921b-104">構文</span><span class="sxs-lookup"><span data-stu-id="d921b-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d921b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d921b-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="d921b-106">[in]メタデータ インターフェイスを指定する参照の ID です。</span><span class="sxs-lookup"><span data-stu-id="d921b-106">[in] The reference ID that specifies the metadata interface.</span></span>  
  
 `ppObj`  
 <span data-ttu-id="d921b-107">[out]アドレスへのポインター、`T:IUnknown`のいずれかであるオブジェクトを[メタデータ インターフェイス](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)します。</span><span class="sxs-lookup"><span data-stu-id="d921b-107">[out] A pointer to the address of an `T:IUnknown` object that is one of the [metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d921b-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="d921b-108">Remarks</span></span>  
 <span data-ttu-id="d921b-109">デバッガーを使用できる、 `GetMetaDataInterface` 、モジュールのモジュールを編集するにはこれを行う必要がありますが、元のメタデータのコピーを作成するメソッド。</span><span class="sxs-lookup"><span data-stu-id="d921b-109">The debugger can use the `GetMetaDataInterface` method to make a copy of the original metadata for a module, which it must do in order to edit that module.</span></span> <span data-ttu-id="d921b-110">デバッガーの呼び出し`GetMetaDataInterface`を取得する、 [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)インターフェイス オブジェクト、モジュールの呼び出し、 [imetadataemit::savetomemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md)モジュールのメタデータのコピーをメモリに保存します。</span><span class="sxs-lookup"><span data-stu-id="d921b-110">The debugger calls `GetMetaDataInterface` to get an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface object for the module, then calls [IMetaDataEmit::SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) to save a copy of the module's metadata to memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d921b-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="d921b-111">Requirements</span></span>  
 <span data-ttu-id="d921b-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d921b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d921b-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d921b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d921b-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d921b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d921b-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d921b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d921b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d921b-116">See also</span></span>
- [<span data-ttu-id="d921b-117">メタデータ</span><span class="sxs-lookup"><span data-stu-id="d921b-117">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
