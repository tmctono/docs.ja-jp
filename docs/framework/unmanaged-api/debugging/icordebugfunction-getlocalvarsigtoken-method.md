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
ms.openlocfilehash: a923701b05f7d283c4fd464d470fb0c9243c1bd5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213609"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="7bb52-102">ICorDebugFunction::GetLocalVarSigToken メソッド</span><span class="sxs-lookup"><span data-stu-id="7bb52-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="7bb52-103">このによって表される関数の、ローカル変数シグネチャのメタデータトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="7bb52-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bb52-104">構文</span><span class="sxs-lookup"><span data-stu-id="7bb52-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bb52-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7bb52-105">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="7bb52-106">入出力`mdSignature`この関数のローカル変数シグネチャのトークンへのポインター `mdSignatureNil` 。この関数にローカル変数がない場合は。</span><span class="sxs-lookup"><span data-stu-id="7bb52-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bb52-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="7bb52-107">Requirements</span></span>  
 <span data-ttu-id="7bb52-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bb52-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bb52-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7bb52-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7bb52-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bb52-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bb52-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bb52-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
