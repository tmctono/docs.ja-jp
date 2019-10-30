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
ms.openlocfilehash: a6f2f536d360ffe41caf2a96c8b051f9167343c2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138956"
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="10c7c-102">ICorDebugStringValue::GetLength メソッド</span><span class="sxs-lookup"><span data-stu-id="10c7c-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="10c7c-103">このによって参照される文字列の文字数を取得します。</span><span class="sxs-lookup"><span data-stu-id="10c7c-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10c7c-104">構文</span><span class="sxs-lookup"><span data-stu-id="10c7c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10c7c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="10c7c-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="10c7c-106">入出力この `ICorDebugStringValue` オブジェクトによって参照される文字列の長さを指定する値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="10c7c-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10c7c-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="10c7c-107">Requirements</span></span>  
 <span data-ttu-id="10c7c-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10c7c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10c7c-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10c7c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10c7c-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10c7c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10c7c-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10c7c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
