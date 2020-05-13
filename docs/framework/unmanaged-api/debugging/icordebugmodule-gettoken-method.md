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
ms.openlocfilehash: a6aff37a480460bfed7064d59b4c5276daf3207c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212504"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="b2f8e-102">ICorDebugModule::GetToken メソッド</span><span class="sxs-lookup"><span data-stu-id="b2f8e-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="b2f8e-103">このモジュールのテーブルエントリのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="b2f8e-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2f8e-104">構文</span><span class="sxs-lookup"><span data-stu-id="b2f8e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2f8e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b2f8e-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="b2f8e-106">入出力`mdModule`モジュールのメタデータを参照するトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b2f8e-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2f8e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="b2f8e-107">Remarks</span></span>  
 <span data-ttu-id="b2f8e-108">トークンは、 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)、 [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)、および[IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md)メタデータインポートインターフェイスに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="b2f8e-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2f8e-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="b2f8e-109">Requirements</span></span>  
 <span data-ttu-id="b2f8e-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2f8e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2f8e-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2f8e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2f8e-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2f8e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2f8e-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2f8e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2f8e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2f8e-114">See also</span></span>

- [<span data-ttu-id="b2f8e-115">メタデータ</span><span class="sxs-lookup"><span data-stu-id="b2f8e-115">Metadata</span></span>](../metadata/index.md)
