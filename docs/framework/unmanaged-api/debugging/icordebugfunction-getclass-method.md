---
title: ICorDebugFunction::GetClass メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetClass
helpviewer_keywords:
- GetClass method, ICorDebugFunction interface [.NET Framework debugging]
- ICorDebugFunction::GetClass method [.NET Framework debugging]
ms.assetid: 27967230-144f-40d3-9e23-961d0241abd9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 218818097846709ec92e20f33a0707314edd562a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754740"
---
# <a name="icordebugfunctiongetclass-method"></a><span data-ttu-id="db811-102">ICorDebugFunction::GetClass メソッド</span><span class="sxs-lookup"><span data-stu-id="db811-102">ICorDebugFunction::GetClass Method</span></span>
<span data-ttu-id="db811-103">この関数のメンバーであるクラスを表す ICorDebugClass オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="db811-103">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db811-104">構文</span><span class="sxs-lookup"><span data-stu-id="db811-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db811-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="db811-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="db811-106">[out]アドレスへのポインター、`ICorDebugClass`オブジェクトを表すクラス、または null の場合、この関数は、クラスのメンバーではない場合。</span><span class="sxs-lookup"><span data-stu-id="db811-106">[out] A pointer to the address of the `ICorDebugClass` object that represents the class, or null, if this function is not a member of a class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db811-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="db811-107">Requirements</span></span>  
 <span data-ttu-id="db811-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="db811-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db811-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db811-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db811-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db811-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db811-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db811-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
