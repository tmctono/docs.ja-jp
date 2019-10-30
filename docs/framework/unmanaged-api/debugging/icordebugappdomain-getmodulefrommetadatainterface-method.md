---
title: ICorDebugAppDomain::GetModuleFromMetaDataInterface メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetModuleFromMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDataInterface
helpviewer_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDatainterface method [.NET Framework debugging]
- GetModuleFromMetaDatainterface method [.NET Framework debugging]
ms.assetid: f35225b3-5dda-4d5a-913d-b3373e9ab81e
topic_type:
- apiref
ms.openlocfilehash: c8469c9aa875e7d567229e9949d83083cbe54987
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110342"
---
# <a name="icordebugappdomaingetmodulefrommetadatainterface-method"></a><span data-ttu-id="e891e-102">ICorDebugAppDomain::GetModuleFromMetaDataInterface メソッド</span><span class="sxs-lookup"><span data-stu-id="e891e-102">ICorDebugAppDomain::GetModuleFromMetaDataInterface Method</span></span>
<span data-ttu-id="e891e-103">指定されたメタデータインターフェイスに対応するモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="e891e-103">Gets the module that corresponds to the given metadata interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e891e-104">構文</span><span class="sxs-lookup"><span data-stu-id="e891e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromMetaDataInterface (  
    [in] IUnknown           *pIMetaData,  
    [out] ICorDebugModule  **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e891e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e891e-105">Parameters</span></span>  
 `pIMetaData`  
 <span data-ttu-id="e891e-106">から[メタデータインターフェイス](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)の1つであるオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e891e-106">[in] A pointer to an object that is one of the [Metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
 `ppModule`  
 <span data-ttu-id="e891e-107">入出力指定されたメタデータインターフェイスに対応するモジュールを表す、モジュールオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e891e-107">[out] A pointer to the address of an ICorDebugModule object that represents the module corresponding to the given metadata interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e891e-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="e891e-108">Requirements</span></span>  
 <span data-ttu-id="e891e-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e891e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e891e-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e891e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e891e-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e891e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e891e-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e891e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
