---
title: ICorDebugFunction::GetLocalVarSigToken メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetLocalVarSigToken
helpviewer_keywords:
- ICorDebugFunction::GetLocalVarSigToken method [.NET Framework debugging]
- GetLocalVarSigToken method [.NET Framework debugging]
ms.assetid: 31e53494-bcc9-4981-91a4-f7e0f02cad48
topic_type:
- apiref
ms.openlocfilehash: c159a175ddd380015cc2dc21637c8b63fd3caea6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137889"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="c9ef2-102">ICorDebugFunction::GetLocalVarSigToken メソッド</span><span class="sxs-lookup"><span data-stu-id="c9ef2-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="c9ef2-103">このによって表される関数の、ローカル変数シグネチャのメタデータトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="c9ef2-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9ef2-104">構文</span><span class="sxs-lookup"><span data-stu-id="c9ef2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9ef2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c9ef2-105">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="c9ef2-106">入出力この関数のローカル変数シグネチャの `mdSignature` トークンへのポインター。または、この関数にローカル変数がない場合は `mdSignatureNil`。</span><span class="sxs-lookup"><span data-stu-id="c9ef2-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9ef2-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="c9ef2-107">Requirements</span></span>  
 <span data-ttu-id="c9ef2-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9ef2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9ef2-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9ef2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9ef2-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9ef2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9ef2-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9ef2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
