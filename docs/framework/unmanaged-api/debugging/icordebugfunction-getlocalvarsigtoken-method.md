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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a682999c888a93cef94162a8179673c862dc43ce
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476647"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="d5748-102">ICorDebugFunction::GetLocalVarSigToken メソッド</span><span class="sxs-lookup"><span data-stu-id="d5748-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="d5748-103">この ICorDebugFunction インスタンスで表される関数のローカル変数シグネチャのメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="d5748-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5748-104">構文</span><span class="sxs-lookup"><span data-stu-id="d5748-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5748-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d5748-105">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="d5748-106">[out]ポインター、 `mdSignature` 、この関数のローカル変数シグネチャのトークンまたは`mdSignatureNil`この関数にローカル変数が存在しません。</span><span class="sxs-lookup"><span data-stu-id="d5748-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5748-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="d5748-107">Requirements</span></span>  
 <span data-ttu-id="d5748-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5748-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5748-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5748-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5748-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5748-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5748-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5748-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
