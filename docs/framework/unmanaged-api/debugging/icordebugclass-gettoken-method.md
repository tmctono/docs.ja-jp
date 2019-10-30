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
ms.openlocfilehash: 6964c931307a40f384ad8a8e355cab0aad575ec6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125770"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="670db-102">ICorDebugClass::GetToken メソッド</span><span class="sxs-lookup"><span data-stu-id="670db-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="670db-103">このクラスの定義を参照する `TypeDef` メタデータトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="670db-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="670db-104">構文</span><span class="sxs-lookup"><span data-stu-id="670db-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="670db-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="670db-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="670db-106">入出力このクラスの定義を参照する `mdTypeDef` トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="670db-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="670db-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="670db-107">Requirements</span></span>  
 <span data-ttu-id="670db-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="670db-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="670db-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="670db-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="670db-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="670db-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="670db-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="670db-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="670db-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="670db-112">See also</span></span>

- [<span data-ttu-id="670db-113">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="670db-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
