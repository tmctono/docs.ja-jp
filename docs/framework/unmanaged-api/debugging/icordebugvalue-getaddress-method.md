---
title: ICorDebugValue::GetAddress メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
ms.openlocfilehash: 906ca2540e421953b3ce39300aa7b2376f789929
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137097"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="d3727-102">ICorDebugValue::GetAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="d3727-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="d3727-103">この "ICorDebugValue" オブジェクトのアドレスを取得します。このオブジェクトはデバッグ中です。</span><span class="sxs-lookup"><span data-stu-id="d3727-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3727-104">構文</span><span class="sxs-lookup"><span data-stu-id="d3727-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3727-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d3727-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="d3727-106">入出力この値オブジェクトのアドレスを指定する `CORDB_ADDRESS` オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d3727-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3727-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d3727-107">Remarks</span></span>  
 <span data-ttu-id="d3727-108">値が使用できない場合は、0 (ゼロ) が返されます。</span><span class="sxs-lookup"><span data-stu-id="d3727-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="d3727-109">これは、値がレジスタの少なくとも一部であるか、ガベージコレクターハンドル (`GCHandle`) に格納されている場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d3727-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3727-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="d3727-110">Requirements</span></span>  
 <span data-ttu-id="d3727-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3727-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3727-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3727-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3727-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3727-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3727-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3727-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3727-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3727-115">See also</span></span>
