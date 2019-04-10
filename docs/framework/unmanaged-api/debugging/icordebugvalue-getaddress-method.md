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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac550ee7b1d66612557b30d15c275c90cf09b8af
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187342"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="96de9-102">ICorDebugValue::GetAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="96de9-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="96de9-103">デバッグ対象プロセスでは、この"ICorDebugValue"オブジェクトのアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="96de9-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96de9-104">構文</span><span class="sxs-lookup"><span data-stu-id="96de9-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96de9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="96de9-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="96de9-106">[out]ポインターを`CORDB_ADDRESS`値オブジェクトのアドレスを指定するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="96de9-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96de9-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="96de9-107">Remarks</span></span>  
 <span data-ttu-id="96de9-108">値が使用できない場合は、0 (ゼロ) が返されます。</span><span class="sxs-lookup"><span data-stu-id="96de9-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="96de9-109">これは、値は、レジスタで少なくとも一部場合に発生する可能性がありますまたはガベージ コレクター ハンドルに格納されている (`GCHandle`)。</span><span class="sxs-lookup"><span data-stu-id="96de9-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96de9-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="96de9-110">Requirements</span></span>  
 <span data-ttu-id="96de9-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="96de9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96de9-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96de9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96de9-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96de9-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="96de9-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="96de9-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="96de9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="96de9-115">See also</span></span>
