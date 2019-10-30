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
ms.openlocfilehash: fb96949e22b4edfc0e64780a54bb38da44eb8369
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129545"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a><span data-ttu-id="2929a-102">ICorDebugModule::GetMetaDataInterface メソッド</span><span class="sxs-lookup"><span data-stu-id="2929a-102">ICorDebugModule::GetMetaDataInterface Method</span></span>
<span data-ttu-id="2929a-103">モジュールのメタデータを調べるために使用できるメタデータインターフェイスオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="2929a-103">Gets a metadata interface object that can be used to examine the metadata for the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2929a-104">構文</span><span class="sxs-lookup"><span data-stu-id="2929a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2929a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2929a-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="2929a-106">からメタデータインターフェイスを指定する参照 ID。</span><span class="sxs-lookup"><span data-stu-id="2929a-106">[in] The reference ID that specifies the metadata interface.</span></span>  
  
 `ppObj`  
 <span data-ttu-id="2929a-107">入出力[メタデータインターフェイス](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)の1つである `T:IUnknown` オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2929a-107">[out] A pointer to the address of an `T:IUnknown` object that is one of the [metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2929a-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="2929a-108">Remarks</span></span>  
 <span data-ttu-id="2929a-109">デバッガーでは、`GetMetaDataInterface` メソッドを使用して、モジュールの元のメタデータのコピーを作成できます。モジュールは、モジュールを編集するために実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2929a-109">The debugger can use the `GetMetaDataInterface` method to make a copy of the original metadata for a module, which it must do in order to edit that module.</span></span> <span data-ttu-id="2929a-110">デバッガーは `GetMetaDataInterface` を呼び出してモジュールの[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)インターフェイスオブジェクトを取得し、 [IMetaDataEmit:: savetomemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md)を呼び出してモジュールのメタデータのコピーをメモリに保存します。</span><span class="sxs-lookup"><span data-stu-id="2929a-110">The debugger calls `GetMetaDataInterface` to get an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface object for the module, then calls [IMetaDataEmit::SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) to save a copy of the module's metadata to memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2929a-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="2929a-111">Requirements</span></span>  
 <span data-ttu-id="2929a-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2929a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2929a-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2929a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2929a-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2929a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2929a-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2929a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2929a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2929a-116">See also</span></span>

- [<span data-ttu-id="2929a-117">メタデータ</span><span class="sxs-lookup"><span data-stu-id="2929a-117">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
