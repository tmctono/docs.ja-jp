---
title: ICorDebugReferenceValue::Dereference メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
ms.openlocfilehash: 7c64823e1a5c519eb74b508af093afeb1132e608
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210086"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="90fbf-102">ICorDebugReferenceValue::Dereference メソッド</span><span class="sxs-lookup"><span data-stu-id="90fbf-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="90fbf-103">参照されているオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="90fbf-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90fbf-104">構文</span><span class="sxs-lookup"><span data-stu-id="90fbf-104">Syntax</span></span>  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90fbf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="90fbf-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="90fbf-106">入出力この値のオブジェクトが指すオブジェクトを表す ICorDebugValue のアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="90fbf-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90fbf-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="90fbf-107">Remarks</span></span>  
 <span data-ttu-id="90fbf-108">`ICorDebugValue`オブジェクトは、その参照がまだ無効になっていない場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="90fbf-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90fbf-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="90fbf-109">Requirements</span></span>  
 <span data-ttu-id="90fbf-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90fbf-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90fbf-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90fbf-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90fbf-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90fbf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90fbf-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90fbf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
