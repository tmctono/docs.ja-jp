---
title: ICorDebugVariableHome::GetLocationType メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b7b95c79b41737ade42e6a9a2741f9c43a41130
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774470"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="de57c-102">ICorDebugVariableHome::GetLocationType メソッド</span><span class="sxs-lookup"><span data-stu-id="de57c-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="de57c-103">変数のネイティブの場所の種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="de57c-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de57c-104">構文</span><span class="sxs-lookup"><span data-stu-id="de57c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de57c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="de57c-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="de57c-106">[out]変数のネイティブの場所の種類へのポインター。</span><span class="sxs-lookup"><span data-stu-id="de57c-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="de57c-107">参照してください、 [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)詳細情報を列挙します。</span><span class="sxs-lookup"><span data-stu-id="de57c-107">See the [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de57c-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="de57c-108">Requirements</span></span>  
 <span data-ttu-id="de57c-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="de57c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de57c-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de57c-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de57c-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de57c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de57c-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de57c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de57c-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="de57c-113">See also</span></span>

- [<span data-ttu-id="de57c-114">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de57c-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [<span data-ttu-id="de57c-115">VariableLocationType 列挙型</span><span class="sxs-lookup"><span data-stu-id="de57c-115">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
