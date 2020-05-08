---
title: ICorDebugEnum::GetCount メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::GetCount
helpviewer_keywords:
- ICorDebugEnum::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: d8a74304-1cb2-4977-a21d-e1af48c563ff
topic_type:
- apiref
ms.openlocfilehash: 90ba690897abced2d4f6282eedef91712d8ceeca
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976344"
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="c0d5a-102">ICorDebugEnum::GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="c0d5a-102">ICorDebugEnum::GetCount Method</span></span>
<span data-ttu-id="c0d5a-103">列挙に含まれる項目の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="c0d5a-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0d5a-104">構文</span><span class="sxs-lookup"><span data-stu-id="c0d5a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0d5a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0d5a-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="c0d5a-106">入出力列挙体に含まれる項目の数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c0d5a-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0d5a-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="c0d5a-107">Requirements</span></span>  
 <span data-ttu-id="c0d5a-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0d5a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0d5a-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0d5a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0d5a-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0d5a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0d5a-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0d5a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
