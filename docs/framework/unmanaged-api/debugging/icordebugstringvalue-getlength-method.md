---
title: ICorDebugStringValue::GetLength メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b13fe65f892a222abb126aa9237b802507738b7f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771609"
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="9217a-102">ICorDebugStringValue::GetLength メソッド</span><span class="sxs-lookup"><span data-stu-id="9217a-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="9217a-103">この ICorDebugStringValue によって参照される文字列の文字数を取得します。</span><span class="sxs-lookup"><span data-stu-id="9217a-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9217a-104">構文</span><span class="sxs-lookup"><span data-stu-id="9217a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9217a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9217a-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="9217a-106">[out]これによって参照される文字列の長さを指定する値へのポインター`ICorDebugStringValue`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9217a-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9217a-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="9217a-107">Requirements</span></span>  
 <span data-ttu-id="9217a-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9217a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9217a-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9217a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9217a-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9217a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9217a-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9217a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
