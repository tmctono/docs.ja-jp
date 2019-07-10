---
title: ICorDebugModule::GetGlobalVariableValue メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetGlobalVariableValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetGlobalVariableValue
helpviewer_keywords:
- ICorDebugModule::GetGlobalVariableValue method [.NET Framework debugging]
- GetGlobalVariableValue method [.NET Framework debugging]
ms.assetid: bbc0881c-6a59-41a0-b5ee-2f3d1b71684c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd79299dcfdb03b703c2cab214ba448631daa6f2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763482"
---
# <a name="icordebugmodulegetglobalvariablevalue-method"></a><span data-ttu-id="69f38-102">ICorDebugModule::GetGlobalVariableValue メソッド</span><span class="sxs-lookup"><span data-stu-id="69f38-102">ICorDebugModule::GetGlobalVariableValue Method</span></span>
<span data-ttu-id="69f38-103">指定されたグローバル変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="69f38-103">Gets the value of the specified global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69f38-104">構文</span><span class="sxs-lookup"><span data-stu-id="69f38-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGlobalVariableValue(  
    [in]  mdFieldDef      fieldDef,  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69f38-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="69f38-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="69f38-106">[in]`mdFieldDef`グローバル変数を記述するメタデータを参照するトークン。</span><span class="sxs-lookup"><span data-stu-id="69f38-106">[in] An `mdFieldDef` token that references the metadata describing the global variable.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="69f38-107">[out]指定されたグローバル変数の値を表す ICorDebugValue オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="69f38-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified global variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69f38-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="69f38-108">Requirements</span></span>  
 <span data-ttu-id="69f38-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="69f38-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69f38-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69f38-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69f38-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69f38-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69f38-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69f38-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
