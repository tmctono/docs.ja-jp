---
title: ICorDebugModule::GetToken メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type:
- apiref
ms.openlocfilehash: 683c2853ea2ed43e61eb666ec56619cb58cde273
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129498"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="d05ae-102">ICorDebugModule::GetToken メソッド</span><span class="sxs-lookup"><span data-stu-id="d05ae-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="d05ae-103">このモジュールのテーブルエントリのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d05ae-104">構文</span><span class="sxs-lookup"><span data-stu-id="d05ae-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d05ae-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d05ae-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="d05ae-106">入出力モジュールのメタデータを参照する `mdModule` トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d05ae-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d05ae-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d05ae-107">Remarks</span></span>  
 <span data-ttu-id="d05ae-108">トークンは、 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)、 [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)、および[IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)メタデータインポートインターフェイスに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="d05ae-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d05ae-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="d05ae-109">Requirements</span></span>  
 <span data-ttu-id="d05ae-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d05ae-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d05ae-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d05ae-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d05ae-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d05ae-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d05ae-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d05ae-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d05ae-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d05ae-114">See also</span></span>

- [<span data-ttu-id="d05ae-115">メタデータ</span><span class="sxs-lookup"><span data-stu-id="d05ae-115">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
