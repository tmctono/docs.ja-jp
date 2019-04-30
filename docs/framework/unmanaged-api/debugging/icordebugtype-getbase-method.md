---
title: ICorDebugType::GetBase メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d04bc67013a2227f295ac3a41be027b9f9b04e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946311"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="25605-102">ICorDebugType::GetBase メソッド</span><span class="sxs-lookup"><span data-stu-id="25605-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="25605-103">1 つが存在する場合、これによって表される型の基本の型を表す、ICorDebugType へのインターフェイス ポインターを取得`ICorDebugType`します。</span><span class="sxs-lookup"><span data-stu-id="25605-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25605-104">構文</span><span class="sxs-lookup"><span data-stu-id="25605-104">Syntax</span></span>  
  
```  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25605-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="25605-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="25605-106">[out]アドレスへのポインター、`ICorDebugType`基本データ型を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="25605-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25605-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="25605-107">Remarks</span></span>  
 <span data-ttu-id="25605-108">型の基本型の検索は、オブジェクトまたはその親クラスのすべてのフィールドの印刷などの一般的なデバッガー機能を実装するために便利です。</span><span class="sxs-lookup"><span data-stu-id="25605-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25605-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="25605-109">Requirements</span></span>  
 <span data-ttu-id="25605-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="25605-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25605-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25605-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25605-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25605-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25605-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25605-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
