---
title: ICorDebugClass::GetModule メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetModule
helpviewer_keywords:
- GetModule method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetModule method [.NET Framework debugging]
ms.assetid: 87029cc4-e5e1-42d5-8b98-655bb7ece520
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 205b7670bac55d428d7458b7accaee5e00b00b03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745589"
---
# <a name="icordebugclassgetmodule-method"></a><span data-ttu-id="c87bf-102">ICorDebugClass::GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="c87bf-102">ICorDebugClass::GetModule Method</span></span>
<span data-ttu-id="c87bf-103">このクラスを定義するモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="c87bf-103">Gets the module that defines this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c87bf-104">構文</span><span class="sxs-lookup"><span data-stu-id="c87bf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule    **pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c87bf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c87bf-105">Parameters</span></span>  
 `pModule`  
 <span data-ttu-id="c87bf-106">[out]このクラスが定義されているモジュールを表す ICorDebugModule オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c87bf-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this class is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c87bf-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="c87bf-107">Requirements</span></span>  
 <span data-ttu-id="c87bf-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c87bf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c87bf-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c87bf-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c87bf-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c87bf-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c87bf-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c87bf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
