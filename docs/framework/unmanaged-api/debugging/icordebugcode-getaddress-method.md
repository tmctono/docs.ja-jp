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
ms.openlocfilehash: df73663f714b0c1c3d3ae5dfb53e8e84196a8f37
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125684"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="00fe3-102">ICorDebugCode::GetAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="00fe3-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="00fe3-103">この "" コード "インターフェイスが表すコードセグメントの相対仮想アドレス (RVA) を取得します。</span><span class="sxs-lookup"><span data-stu-id="00fe3-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00fe3-104">構文</span><span class="sxs-lookup"><span data-stu-id="00fe3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00fe3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="00fe3-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="00fe3-106">入出力コードセグメントの RVA へのポインター。</span><span class="sxs-lookup"><span data-stu-id="00fe3-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00fe3-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="00fe3-107">Requirements</span></span>  
 <span data-ttu-id="00fe3-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00fe3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00fe3-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00fe3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00fe3-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00fe3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00fe3-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00fe3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
