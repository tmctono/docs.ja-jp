---
title: ICorDebugHandleValue::GetHandleType メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.GetHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::GetHandleType
helpviewer_keywords:
- GetHandleType method [.NET Framework debugging]
- ICorDebugHandleValue::GetHandleType method [.NET Framework debugging]
ms.assetid: d5e7b12d-835a-4e86-ae2f-d658d4f1c67c
topic_type:
- apiref
ms.openlocfilehash: 6eb76ddd6ee8b2a00aac3af9ebf815338d29f194
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212166"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="a310d-102">ICorDebugHandleValue::GetHandleType メソッド</span><span class="sxs-lookup"><span data-stu-id="a310d-102">ICorDebugHandleValue::GetHandleType Method</span></span>
<span data-ttu-id="a310d-103">この値オブジェクトによって参照されるハンドルの種類を示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="a310d-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a310d-104">構文</span><span class="sxs-lookup"><span data-stu-id="a310d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a310d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a310d-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="a310d-106">入出力このハンドルの型を示す CorDebugHandleType 列挙値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a310d-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a310d-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="a310d-107">Requirements</span></span>  
 <span data-ttu-id="a310d-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a310d-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a310d-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a310d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a310d-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a310d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a310d-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a310d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
