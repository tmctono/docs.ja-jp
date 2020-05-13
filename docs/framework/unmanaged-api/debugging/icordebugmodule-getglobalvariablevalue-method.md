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
ms.openlocfilehash: 7e32f3f4f6613d34e2b40946ed3eadb8eb0a7c1f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212569"
---
# <a name="icordebugmodulegetglobalvariablevalue-method"></a><span data-ttu-id="f573b-102">ICorDebugModule::GetGlobalVariableValue メソッド</span><span class="sxs-lookup"><span data-stu-id="f573b-102">ICorDebugModule::GetGlobalVariableValue Method</span></span>
<span data-ttu-id="f573b-103">指定したグローバル変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="f573b-103">Gets the value of the specified global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f573b-104">構文</span><span class="sxs-lookup"><span data-stu-id="f573b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGlobalVariableValue(  
    [in]  mdFieldDef      fieldDef,  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f573b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f573b-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="f573b-106">から`mdFieldDef`グローバル変数を記述するメタデータを参照するトークン。</span><span class="sxs-lookup"><span data-stu-id="f573b-106">[in] An `mdFieldDef` token that references the metadata describing the global variable.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="f573b-107">入出力指定されたグローバル変数の値を表す ICorDebugValue オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f573b-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified global variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f573b-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="f573b-108">Requirements</span></span>  
 <span data-ttu-id="f573b-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f573b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f573b-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f573b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f573b-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f573b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f573b-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f573b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
