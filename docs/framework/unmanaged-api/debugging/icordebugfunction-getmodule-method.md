---
title: ICorDebugFunction::GetModule メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetModule
helpviewer_keywords:
- ICorDebugFunction::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 5031a5d3-2564-412a-9007-e36d4631308a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cefe84c482df3b20b5939e031ad76647f295d3e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995614"
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="bf910-102">ICorDebugFunction::GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="bf910-102">ICorDebugFunction::GetModule Method</span></span>
<span data-ttu-id="bf910-103">この関数が定義されているモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="bf910-103">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf910-104">構文</span><span class="sxs-lookup"><span data-stu-id="bf910-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf910-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bf910-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="bf910-106">[out]この関数が定義されているモジュールを表す ICorDebugModule オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bf910-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf910-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="bf910-107">Requirements</span></span>  
 <span data-ttu-id="bf910-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf910-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf910-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf910-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf910-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf910-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf910-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf910-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
