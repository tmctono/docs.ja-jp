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
ms.openlocfilehash: f5d0dd7a99087b21a5f827e4dce0f6342ae7b25a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501769"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a><span data-ttu-id="61925-102">ICorDebugModule::GetMetaDataInterface メソッド</span><span class="sxs-lookup"><span data-stu-id="61925-102">ICorDebugModule::GetMetaDataInterface Method</span></span>
<span data-ttu-id="61925-103">モジュールのメタデータを調べるために使用できるメタデータインターフェイスオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="61925-103">Gets a metadata interface object that can be used to examine the metadata for the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61925-104">構文</span><span class="sxs-lookup"><span data-stu-id="61925-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61925-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="61925-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="61925-106">からメタデータインターフェイスを指定する参照 ID。</span><span class="sxs-lookup"><span data-stu-id="61925-106">[in] The reference ID that specifies the metadata interface.</span></span>  
  
 `ppObj`  
 <span data-ttu-id="61925-107">入出力`T:IUnknown`[メタデータインターフェイス](../metadata/metadata-interfaces.md)の1つであるオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="61925-107">[out] A pointer to the address of an `T:IUnknown` object that is one of the [metadata interfaces](../metadata/metadata-interfaces.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61925-108">解説</span><span class="sxs-lookup"><span data-stu-id="61925-108">Remarks</span></span>  
 <span data-ttu-id="61925-109">デバッガーは、メソッドを使用して `GetMetaDataInterface` モジュールの元のメタデータのコピーを作成できます。モジュールは、モジュールを編集するために実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61925-109">The debugger can use the `GetMetaDataInterface` method to make a copy of the original metadata for a module, which it must do in order to edit that module.</span></span> <span data-ttu-id="61925-110">デバッガーはを呼び出して、 `GetMetaDataInterface` モジュールの[IMetaDataEmit](../metadata/imetadataemit-interface.md) interface オブジェクトを取得し、 [IMetaDataEmit:: savetomemory](../metadata/imetadataemit-savetomemory-method.md)を呼び出してモジュールのメタデータのコピーをメモリに保存します。</span><span class="sxs-lookup"><span data-stu-id="61925-110">The debugger calls `GetMetaDataInterface` to get an [IMetaDataEmit](../metadata/imetadataemit-interface.md) interface object for the module, then calls [IMetaDataEmit::SaveToMemory](../metadata/imetadataemit-savetomemory-method.md) to save a copy of the module's metadata to memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61925-111">要件</span><span class="sxs-lookup"><span data-stu-id="61925-111">Requirements</span></span>  
 <span data-ttu-id="61925-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61925-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61925-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61925-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61925-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61925-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61925-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61925-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61925-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="61925-116">See also</span></span>

- [<span data-ttu-id="61925-117">Metadata</span><span class="sxs-lookup"><span data-stu-id="61925-117">Metadata</span></span>](../metadata/index.md)
