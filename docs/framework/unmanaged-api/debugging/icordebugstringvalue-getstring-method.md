---
title: ICorDebugStringValue::GetString メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetString
helpviewer_keywords:
- ICorDebugStringValue::GetString method [.NET Framework debugging]
- GetString method, ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: 2b94bda7-09ee-435d-91b9-c4e31af1896c
topic_type:
- apiref
ms.openlocfilehash: e23133176cbd703a58c92f9bf1ead530b0bbb8a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178502"
---
# <a name="icordebugstringvaluegetstring-method"></a><span data-ttu-id="a104c-102">ICorDebugStringValue::GetString メソッド</span><span class="sxs-lookup"><span data-stu-id="a104c-102">ICorDebugStringValue::GetString Method</span></span>
<span data-ttu-id="a104c-103">この ICorDebug 文字列値によって参照される文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="a104c-103">Gets the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a104c-104">構文</span><span class="sxs-lookup"><span data-stu-id="a104c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]
        WCHAR       szString[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a104c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a104c-105">Parameters</span></span>  
 `cchString`  
 <span data-ttu-id="a104c-106">[in] `szString` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="a104c-106">[in] The size of the `szString` array.</span></span>  
  
 `pcchString`  
 <span data-ttu-id="a104c-107">[アウト]`szString`配列に返される文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a104c-107">[out] A pointer to the number of characters returned in the `szString` array.</span></span>  
  
 `szString`  
 <span data-ttu-id="a104c-108">[アウト]取得した文字列を格納する配列。</span><span class="sxs-lookup"><span data-stu-id="a104c-108">[out] An array that stores the retrieved string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a104c-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="a104c-109">Requirements</span></span>  
 <span data-ttu-id="a104c-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a104c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a104c-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a104c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a104c-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a104c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a104c-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a104c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
