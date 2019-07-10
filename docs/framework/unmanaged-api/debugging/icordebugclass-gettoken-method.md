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
ms.openlocfilehash: b944112ce0b00e84da6243e2e48917e2318b0f1c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746850"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="2bb5e-102">ICorDebugClass::GetToken メソッド</span><span class="sxs-lookup"><span data-stu-id="2bb5e-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="2bb5e-103">取得、`TypeDef`このクラスの定義を参照するメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="2bb5e-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bb5e-104">構文</span><span class="sxs-lookup"><span data-stu-id="2bb5e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bb5e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2bb5e-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="2bb5e-106">[out]ポインター、`mdTypeDef`このクラスの定義を参照するトークン。</span><span class="sxs-lookup"><span data-stu-id="2bb5e-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bb5e-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="2bb5e-107">Requirements</span></span>  
 <span data-ttu-id="2bb5e-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bb5e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bb5e-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2bb5e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2bb5e-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bb5e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bb5e-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bb5e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bb5e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bb5e-112">See also</span></span>

- [<span data-ttu-id="2bb5e-113">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2bb5e-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
