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
ms.openlocfilehash: f9b00d5e34300f1ed16eaddff3bf8e877219f910
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893797"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="a4c8c-102">ICorDebugCode::GetAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="a4c8c-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="a4c8c-103">この "" コード "インターフェイスが表すコードセグメントの相対仮想アドレス (RVA) を取得します。</span><span class="sxs-lookup"><span data-stu-id="a4c8c-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4c8c-104">構文</span><span class="sxs-lookup"><span data-stu-id="a4c8c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4c8c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a4c8c-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="a4c8c-106">入出力コードセグメントの RVA へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a4c8c-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4c8c-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="a4c8c-107">Requirements</span></span>  
 <span data-ttu-id="a4c8c-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4c8c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4c8c-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4c8c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4c8c-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4c8c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4c8c-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4c8c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
