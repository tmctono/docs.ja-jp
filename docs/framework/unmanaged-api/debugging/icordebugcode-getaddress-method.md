---
title: ICorDebugCode::GetAddress メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetAddress
helpviewer_keywords:
- GetAddress method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetAddress method [.NET Framework debugging]
ms.assetid: cc507cb0-df2e-49c2-b32e-0c3271a8df9a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11ced90b88f083eb69b06d197d64a8ef4252f9d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141499"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="f1e29-102">ICorDebugCode::GetAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="f1e29-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="f1e29-103">この"ICorDebugCode"インターフェイスを表すコード セグメントの相対仮想アドレス (RVA) を取得します。</span><span class="sxs-lookup"><span data-stu-id="f1e29-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1e29-104">構文</span><span class="sxs-lookup"><span data-stu-id="f1e29-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1e29-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1e29-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="f1e29-106">[out]コード セグメントの RVA へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f1e29-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1e29-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="f1e29-107">Requirements</span></span>  
 <span data-ttu-id="f1e29-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1e29-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1e29-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1e29-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1e29-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1e29-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f1e29-111">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="f1e29-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f1e29-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1e29-112">See also</span></span>
