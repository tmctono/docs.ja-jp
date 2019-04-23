---
title: ICorDebugClass::GetToken メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetToken
helpviewer_keywords:
- GetToken method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetToken method [.NET Framework debugging]
ms.assetid: ee5c848a-eac4-4462-b07a-07ccd76a75df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4f33bb15a351be5fe8318dcc3339d429dec039e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183704"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="3f818-102">ICorDebugClass::GetToken メソッド</span><span class="sxs-lookup"><span data-stu-id="3f818-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="3f818-103">取得、`TypeDef`このクラスの定義を参照するメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="3f818-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f818-104">構文</span><span class="sxs-lookup"><span data-stu-id="3f818-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f818-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3f818-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="3f818-106">[out]ポインター、`mdTypeDef`このクラスの定義を参照するトークン。</span><span class="sxs-lookup"><span data-stu-id="3f818-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f818-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="3f818-107">Requirements</span></span>  
 <span data-ttu-id="3f818-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f818-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f818-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f818-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f818-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f818-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f818-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f818-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f818-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f818-112">See also</span></span>

- [<span data-ttu-id="3f818-113">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f818-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
